---
title: Networking lab
...

You've already worked with TCP sockets in COA1.
In this lab you'll learn how to add reliability on top of unreliable sockets like UDP.

You'll have enough to do in this lab, we'll not worry about doing it over an actual network.
We've provided a simple network simulator for you.

{.exercise ...}
1. Download <http://www.cs.virginia.edu/luther/COA2/S2020/files/netlab.tar> on a linux system
    (e.g., with `wget http://www.cs.virginia.edu/luther/COA2/S2020/files/netlab.tar`{.bash}).
2. Extract it and enter the directory (e.g., with `tar xvf netlab.tar; cd netlab`{.bash}).
3. Test it with
    
    ````bash
    make
    ./netlab 0
    ````
    
    You should see a welcome message appear, ending with a `!`.
4. Edit `netlab.c` so that you also see messages for `./netlab 1`, `./netlab 2`, etc.
5. Show a TA your code.
    - We expect everyone to finish `./netlab 1` and to make good progress on `./netlab 2`
    - `./netlab 3` is quite a bit harder and is recommended if you have time
{/}

# Our Driver

We provide a network simulation driver program. It has the following pieces:

- Function `void send(size_t len, void* data)`.
    You'll invoke this to simulate sending unreliable packets over a network.
- Function skeleton `void recvd(size_t len, void* data)`.
    You'll fill in details to describe what you would do on a packet receipt.
- Function `int setTimeout(void (*callback)(void*), unsigned long ms, void *arg)`.
    You may invoke this to ask to have `callback` invoked after `ms` milliseconds (`ms * 0.001` seconds),
    passing `arg` as the argument.

    On success, returns a positive identifier that may be used in `clearTimeout`.
    On failure, returns a special error code:
    
    - `0` if `callback` is `NULL`
    - `-1` if `ms` is too far in the future (more than a minute)
    - `-2` if you have too many pending callbacks scheduled (based on an implementation-defined limit guaranteed to be at least 16)
    
    The callback is executed once per `setTimeout` call, assuming it is not cleared with `clearTimeout` first.
- Function `void clearTimeout(int timeoutID)`.
    If `timeoutID` was returned by `setTimeout` and the callback has not yet been invoked,
    unschedules that callback.
    Otherwise, does nothing.
- Function `void waitForAllTimeouts(void)`.
    If there are no pending timeouts, returns immediately.
    Otherwise, blocks until there are not scheduled timeouts left.
    
    Note, if you do not call this function then your program will stop before it receives any messages.
    
# Protocol

Every message must have its first byte be a checksum.
We'll use a very simple checksum for this lab: the xor of all other bytes.

{.example ...} To send the array of bytes `[0, 1, 2, 5]`
you actually send a five-byte message: `[0^1^2^5, 0, 1, 2, 5]`.
{/}

You should send the server a 4-byte message (plus a checksum) to initiate conversation.
The first three bytes should be the ASCII characters for `GET`; the fourth should be an ASCII digit `0` through `9`.
The server will then start sending you messages in discrete packets.

The first three bytes of each packet the server sends will be a checksum, a (1-based) sequence number, and the total sequence count.
Both sequence number and sequence count will be encoded directly as a byte, not using ASCII.

{.example ...} If the server plans to send two packets,
one containing `[3, 1]` and the other `[4, 1, 5]`,
they will actually arrive as
`[1^2^3^1, 1, 2, 3, 1]`
and
`[2^2^4^1^5, 2, 2, 4, 1, 5]`.
{/}

After receiving a message, you should reply with a four-byte message.
The first three bytes should be the ASCII characters for `ACK`; the fourth should be the sequence number you received.
If a message is not delivered, you should reply with the `ACK` of the last message you got in order (or re-send the `GET` if the very first message is not delivered).
However, messages may be delayed in transit and may arrive out of order.
You should wait at least a few seconds before deciding a message will not arrive and re-sending its request.

Each `GET` will give a different message, and with a different level of errors you need to handle.

0. sends the full message without errors
1. sends the message without errors, one a packet at a time, requiring you to `ACK` properly
2. sends messages unreliably; some messages never arrive and need to be re-requested
3. sends messages unreliably; some messages arrive in a corrupted state and need to be re-requested

You may assume that if a message has not arrived after a full second, it will not arrive.



# Tips

- Work with a partner.
- Messages with bad checksums are ignored by the server.
- You only have two kinds of messages you'll ever send. It's probably worth writing helper functions to send them (or just one helper to send both based on an argument).
- `ACK`0 does not work; use `GET` instead.
- Make a simple program that uses the `setTimeout` to print something or the like, just to make sure you understand how it works.
    
    {.example ...}The following prints 3, then 1, then 4, ending two seconds after it started.

    ````c
    void pnum(void *num) {
        printf("%d\n", (int)num);
    }
    int main() {
        int one = setTimeout(pnum, 1000, (void *)1uL);
        int two = setTimeout(pnum, 500, (void *)2uL);
        int three = setTimeout(pnum, 100, (void *)3uL);
        int four = setTimeout(pnum, 2000, (void *)4uL);
        clearTimeout(two);
        waitForAllTimeouts();
    }
    ````
    {/}
    
    
- The argument of your callbacks must be typed as a `void *`, but (via casting) can be any type of 8 or fewer bytes.
    Feel free to use `NULL` if you don't need an argument.
- My solution used a few global variables for the information I wanted in every callback. It was 58 lines of reasonably-formatted C code.
