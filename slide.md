class: center, middle

#TDD เปลี่ยนชีวิตคนคนนี้ยังไง
###@barcampSK4

---

# Me?

.right[![](https://avatars0.githubusercontent.com/u/686676?v=3&s=460)]

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


- ## Debug is hell !!!

- ## Testing to painful ?

- ## Dont know wrong on which version ?

---
class: center, middle

# TDD =  Test Driven Developement
## Test + Driven

---

# Testing
Manual Testing

```sh
$ python cut_grade.py
> 81
A
> 70
B
> 49
E
> -1
exit
```
This is only 3 cases.
--

##How about 84 cases? Ten Times ?

---

# Testing
## Automate Testng
3 cases.
```sh
$ nosetests tests/cut_grade_test.py -v
test_give_81_should_be_A ... passed
test_give_70_should_be_B ... passed
test_give_49_should_be_E ... passed
---------------------------------------------
3 tests run in 0.0 seconds (3 tests passed)
```
--
84 cases.
```sh
$nosetests
................................................
....................................
-----------------------------------------------------------
84 tests run in 0.0 seconds (84 tests passed)
```
---
# How automate test look like ?

```python
def test_score_81_get_A(self):
  score = 81
  grade = cut_grade(score)
  self.assertEqual(grade,'A')

def test_score_70_get_B(self):
  score = 70
  grade = cut_grade(score)
  self.assertEqual(grade,'B')

def test_ score_49_get_E(self):
  score = 49
  grade = cut_grade(score)
  self.assertEqual(grade,'E')
```

---

# Benefit of Testing

## Know your software is working
-- code working
-- work on system / device / dependency version ?
## Know what wrong
-- your code fail
-- system not support
## Fast feedback
-- change to fix.

---
# Pitfall of Testing

## Make it work, (write) Test Later
-- Technique debt. You pay what you play.
## Small project don't write test !!!
-- Every code should have test.  
-- Testcase is your document.  
-- Try in small project then appiled in real-world project later.

---
# Pitfall of TDD

## Make your work slow
-- You can drive faster because of break.
## Don't have to design

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
