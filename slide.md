#TDD เปลี่ยนชีวิตคนคนนี้ยังไง
###@barcampSK41

---

# Me?

```sh
$ who
> Teerasak Kroputaponchai
> http://dev.im-bot.com
> https://github.com/ibotdotout

$ do
> Python
> Automate Testing
> Automation Workflow
> Dev-ops
> Agile / XP
```

---
#Problem


## Debug is hell !!!

## Testing to painful ?

## Dont know wrong on which version ?

---

# TDD =  Test Driven Developement
## Test + Driven

---

# Testing
Manual Testing

```sh
$ python cut_grade.py> 81A> 70B> 49E> -1exit
```
This is only 3 cases.  How about 84 cases? Ten Times ?

----

# Testing
## Automate Testng
3 cases.
```sh
$ nosetests tests/cut_grade_test.py -vtest_give_81_should_be_A ... passedtest_give_70_should_be_B ... passedtest_give_49_should_be_E ... passed---------------------------------------------3 tests run in 0.0 seconds (3 tests passed)
```
84 cases.
```sh
$ nosetests....................................................................................-----------------------------------------------------------------------------84 tests run in 0.0 seconds (84 tests passed)6 / 18How automate test look like ?
def test_score_81_get_A(self):    score = 81    grade = cut_grade(score)    self.assertEqual(grade,'A')def test_score_70_get_B(self):    score = 70    grade = cut_grade(score)    self.assertEqual(grade,'B')def test_score_49_get_E(self):    score = 49    grade = cut_grade(score)    self.assertEqual(grade,'E')
```

---

# Benefit of Testing

Know your software is working
--- code working
--- work on system / device / dependency version ?
Know what wrong
-- your code fail
-- system not support
Fast feedback
--- change to fix.

---
# Pitfall of Testing

Make it work, (write) Test Later
-- Technique debt.
Small project don't write test !!!
-- Every code should have test. Testcase is your document.

---
# Test Driven = (Write) Test first

---
# Why

---
# Why test first

Think What not How ?
-- Think What it does, not how it implement.
Focus on your task and Prevent Over Design
-- Do The Simplest Thing That Could Possibly Work #DTSTTCPW
Make Testable Code.
-- Not every code that easy to test.

---
# What wrong with test after ?

Hard to test
-- Your code not design to be testable.
Your task done, why not rest ?
-- Your never comeback to write test.
Write test to passed your code. What !!!
-- You should write code to passed your test.

---

# TDD Life Cycle


Add testcase
Look test fail
Write Code
Run tests
Refactor

---
# TDD - Divide and Conquer

Q: Canculate area under curve ?A: Cut into small piece and calcuclate area than sum all area.
Benefits

Small Task
Focus
Progress
No fear
Achievements

---

# Live Demo (Unittest)

---
# Next ?

Integration Testing
-- etc. Database
UI Testing
-- etc. Web, Mobile
Automate Workflow
-- Veriosn Control, Automate Code Review,  Continous Integration, Automate Deploy

---
# References:

Tdd by http://www.somkiat.cc
