---
title: Policies
...

# Course objectives

This course is intended to expose how computers actually work
ranging from out-of-order execution to operating system features,
with a focus on topics related to concurrency and security.
At the end of it, you will be able to

- Reason about how memory works, including caches and virtual memory
- Understand modern security exploits, including meltdown and spectre
- Reason abotu concurrency, including deadlock and race conditions
- Implement concurrency with low-levle primitives
- Use make and related build tools


# Logistics

## Meetings

Lecture is optional but strongly encouraged.
Monday, Wednesday, and Friday, 2:00–2:50, online.

There are two lab sections:
one on Tuesday 5:00--6:15 pm
and the other on Tuesday 6:30--7:45 pm.
Please attend your assigned lab section.

I do not schedule review sessions or the like outside of usual class time.


## Tasks

The exact details of course assignments are still being determined.
However, we do know you will be asked to

- Participate in lab
    - Labs are primarily learning exercises and most credit is for participation, but learning only occurs if sufficient progress is made so each lab has milestones that need to be reached for full credit.
    - We expect everyone to be ill, need to travel, or otherwise miss one lab, which will be excused without the need to provide documentation of your situation. To be excused for more than one lab, documentation of why each was missed is needed.
- Do homework
    - Each homework is an individual assignment unless otherwise announced.
    - Some homework will be programming assignments; others will be puzzles, worksheets, or other kinds of activities.
- Take quizzes
    - We will have weekly quizzes, administered online.
- Take exams
    - Exams will either be in-class or in-lab and must be taken in person..


## Contact

|        | Instructor | TAs |
|--------|------------|-----|
| Name | Luther Tychonievich | Dylan Cao, Anders Christoffersen, Rashid Lasker, William Mayes, Gustavo Moreira |
| Office Hours | Mo 3-4; Tu 10-11; We 11-12; Th 2-3 | See the [OH page](oh.html)  |
| Phone | 243-3789 | (none) |
| Email | <a href="mailto:tychonievich@virginia.edu?subject=COA2">tychonievich@virginia.edu</a> | use [Piazza](https://piazza.com/class/k571ccotjhd55) |

For communication about course content, [Piazza](https://piazza.com/class/k571ccotjhd55) is preferred to email.
For communication about personal circumstances, email or in-person visits are preferred.
If you email, include "COA2" in the subject line to prevent your email from skipping my inbox and never getting read.

## Readings

Although we have several textbooks we are considering for use,
none of them were settled on for this pilot.
Readings written by us or selected from articles or web pages will periodically be posted on the schedule.
Some of these may have "reading quizzes" associated with them:
quizzes to be taken based on the reading prior to the lecture in which they are discussed.

## Coding

> "If you really want to understand something, the best way is to try and explain it to someone else. That forces you to sort it out in your own mind. And the more slow and dim-witted your pupil, the more you have to break things down into more and more simple ideas. And that’s really the essence of programming. By the time you’ve sorted out a complicated idea into little steps that even a stupid machine can deal with, you’ve certainly learned something about it yourself."
> <div>---Douglas Adams</div>

This course will involve multiple programming assignments in C (and maybe a bit of other languages).

Estimating how long it will take someone to complete a coding assignment
is always difficult.
The target difficulty is 5–10 hours of focused effort each week.

# Grading

[Grading](http://www.cs.virginia.edu/tychonievich/blog/posts/244.html) is one of the aspects of a course that instructors enjoy even less than students. Still, we are stuck with them, so here goes.

## Points per Activity Type

Since this course has not been offered before, we may adjust these weights as the semester progresses.
Any such adjustment will be discussed in class before being implemented.

Task | Weight | Comments
-----|--------|-----------------------------------------------------------------
Quizzes     | 10% | Drop lowest score
Labs  		| 10% | Drop lowest score
Assignments | 40% | 
Exams  		| 40% |

Your final grade is computed based on the percentage of points you have earned and is designed to match the GPA value of each letter. For reasons I do not understand, that is not a linear scale: for example, `A-` &minus; `B+` = 0.4 grade points while `B+` &minus; `B` = 0.3 grade points. For reasons even farther from my ken, the most common grading scale I have seen is also not linear but differently spaced than the grade points (using \_7 instead of \_6 below). Following is a scale spaced like the grade point scale:

You get     if you score     Which is worth     Notes
----------  ------------    ----------------    ------------------
A+          near the top           4.0          CR; meets prereqs as C&minus; or better in CS 3330
A           &ge; 93%               4.0          CR; meets prereqs as C&minus; or better in CS 3330
A&minus;    &ge; 90%               3.7          CR; meets prereqs as C&minus; or better in CS 3330
B+          &ge; 86%               3.3          CR; meets prereqs as C&minus; or better in CS 3330
B           &ge; 83%               3.0          CR; meets prereqs as C&minus; or better in CS 3330
B&minus;    &ge; 80%               2.7          CR; meets prereqs as C&minus; or better in CS 3330
C+          &ge; 76%               2.3          CR; meets prereqs as C&minus; or better in CS 3330
C           &ge; 70%               2.0          CR; meets prereqs as C&minus; or better in CS 3330
C&minus;    *removed*                           *C&minus; removed this semester* 
D+          &ge; 66%               1.3          GC; meets degree req
D           &ge; 63%               1.0          GC; meets degree req
D&minus;    &ge; 60%               0.7          GC; meets degree req
F           otherwise              0.0          NC; does not meet any req

## Submitting late

Quiz solutions are released the moment the quiz closes, and thus quizzes cannot be taken late.
Your lowest quiz score is dropped.

Assignments may be submitted up to 48 hours late.
They are given 90% credit between 0 and 24 hours late;
at 80% credit between 24 and 48 hours late.
If extensions beyond that time are needed, please see the professor to discuss why and if other accommodations are also needed.

Exams may not be taken late without special-case permission.

# Miscellanea

## Professionalism

Behave professionally.

Never abuse anyone, including the emotional abuse of blaming others for your mistakes.
Kindness is more important than correctness.

Let our TAs be students when they are not being TAs.

## Honesty

I always hope everyone will behave honestly.
I know we all are tempted to do what we ought not;
if you do something you regret, the sooner you tell me the sooner (and more leniently) we can correct it.

### No plagiarism (nor anything like it)

You **must** cite any and every source you consult, other than those explicitly provided by the course itself.
Talked to a friend, saw an interesting video, consulted a website, had a tutor?
Tell us!
Put it in a comment in your code.

### Write your own code

You must write your own code.
Not just type it (though you need to do that too): **compose it yourself**, as your own original work.
Beware of looking at other students code or code you find online: it is hard to unsee and can spoil your ability to compose your own solutions!

### Understand what you submit

Working together can help you learn. But make sure you learned!
We may ask you to explain aspects of a solution you turn in,
and may dock points if it appears you simply copied someone else's ideas (or just guessed a lot of things until one worked) without understanding them.

### No help on quizzes

It would probably go without saying if we didn't say it, but no assistance may be given or received on any supervised evaluation or online quiz unless specifically announced otherwise by the professor (or another proctor of the evaluation).

### Consequences of Dishonesty

If I believe you have acted dishonestly, I will communicate this fact to you and propose a penalty.
If you have information I lack, please share that with me; I may thereafter change my belief and/or proposed penalty.

If we are not able to come to an agreement, or if the case is particularly egregious and beyond my comfort level handling in-course, we will instead refer the case to the University Honor System and abide by their findings.


## Personal accommodations

### Disability

If you qualify for accommodations from [the SDAC](http://studenthealth.virginia.edu/sdac), please let me know, preferably in my office where we can discuss how your accommodations will interplay with the quiz- and assignment-based nature of this course.

### Religious observances

As a religious person myself, I fully support [the university's stance](https://eocr.virginia.edu/accommodations-religious-observance) on accommodating religious observances.
If such observances or other religious beliefs impact or are likely to impact your work this semester,
please let me know as soon as you are aware of this impact.

### Life

Bad things happen.
People forget things and make mistakes.
Bad days coincide with due dates.
Etc.

If you believe that circumstances warrant an change in deadline, a second chance, or some other accommodation in order to more accurately synchronize grade with knowledge, come talk to me and we'll resolve the situation as best we can.
