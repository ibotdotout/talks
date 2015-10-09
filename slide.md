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
```
--

```sh
$ do
> Python
> Automate Testing
> Automation Workflow
> Dev-ops
> Agile / XP
```

---
class: center, middle

# TDD =  Test Driven Developement
## Test + Driven

---
# Life before TDD

- ## Debug is hell !!!

- ## Testing to painful ?

- ## Dont know wrong on which version ?

---

# Life after TDD

---
class: center, middle
# Testing
## Manual vs Automate

---
# Manual Testing

There are only 3 grades: A, B, F
```sh
$ python cut_grade.py
> 81
A
> 70
B
> 49
F
```
--
Improve to have 5 grades: A, B, C, D, F
```sh
$ python cut_grade.py
> 60
C
> 55
D
```
Test only task you work !!!

---

# Automate Testing
There are only 3 grade: A, B, F
```sh
$ nosetests tests/cut_grade_test.py -v
test_give_81_should_be_A ... passed
test_give_70_should_be_B ... passed
test_give_49_should_be_F ... passed
---------------------------------------------
3 tests run in 0.0 seconds (3 tests passed)
```
--
Improve to have 5 grades: A, B, C, D, F
```sh
$ nosetests tests/cut_grade_test.py -v
test_give_81_should_be_A ... passed
test_give_70_should_be_B ... passed
test_give_60_should_be_C ... failed
test_give_55_should_be_D ... passed
test_give_49_should_be_F ... passed
---------------------------------------------
5 tests run in 0.0 seconds (4 tests passed)
```
Test it All
---
# How automate test look like ?

```python
# AAA - Arrange Act Assert

def test_score_81_get_A(self):
  # Arrage
  score = 81

  # ACT
  grade = cut_grade(score)

  # Assert
  self.assertEqual(grade,'A')

def test_score_70_get_B(self):
  score = 70
  grade = cut_grade(score)
  self.assertEqual(grade,'B')

def test_score_49_get_F(self):
  score = 49
  grade = cut_grade(score)
  self.assertEqual(grade,'F')
```

---

class: center, middle
# Testable Code
### Not every code that testable

---

# Untestable Code

Code
```python
# cut_grade
                  # Act     -> failed
x = int(input())  # Arrange -> failed
if x >= 80:
  print('A')      # Assert  -> failed
elif x >= 70:
  print('B')
else:
  print('F')
```

Test
```python
How ?
```



---

# Untestable Code (Cont.)

Code
```python
def cut_grade(score): # Act -> passed, Arrange-> passed
  if score >= 80:
    print('A')        # Assert -> failed
  elif score >= 70:
    print('B')
  else:
    print('F')

if __name__ == '__main__':
  score = int(input())
  cut_grade(score)
```

Test
```python
def test_score_49_get_F(self):
  score = 49
  cut_grade(score)
  # output is on stdout how to check !!!
```

---
# Testable Code

Code
```python
def cut_grade(score): # Act -> passed, Arrange-> passed
  if score >= 80:
    return 'A'        # Assert -> passed
  elif score >= 70:
    return 'B'
  else:
    return 'F'

if __name__ == '__main__':
  score = int(input())
  grade = cut_grade(score)
  print(grade)
```

Testcase
```python
def test_score_49_get_F(self):
  score = 49
  grade = cut_grade(score)
  self.assertEqual(grade,'F')
```

---

class: center, middle
# Befefit & Pitfall of Testing

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
class: center, middle
# Test Driven = (Write) Test first

---
# Why
<iframe width="720" height="480"
src="https://www.youtube.com/embed/dYim_QZqppY" frameborder="0"
allowfullscreen></iframe>

---
# Why test first

- ## Think What not How ?
-- Think What it does, not how it implement.
- ## Focus on your task and Prevent Over Design
-- Do The Simplest Thing That Could Possibly Work #DTSTTCPW
- ## Make Testable Code.
-- Not every code that easy to test.

---
# What wrong with test after ?

- ## Hard to test
-- Your code not design to be testable.
- ## Your task done, why not rest ?
-- Your never comeback to write test.
- ## Write test to passed your code. What !!!
-- You should write code to passed your test.

---

# TDD Life Cycle

- Add testcase
- Look test fail
- Write Code
- Run tests
- Refactor

---
# TDD - Divide and Conquer

Q: Canculate area under curve ?  
A: Cut into small piece and calcuclate area than sum all area.
Benefits

- Small Task
- Focus
- Progress
- No fear
- Achievements

---
class: center, middle
# Live Demo (Unittest)

---
# Next ?

- ## Integration Testing
-- etc. Database
- ## UI Testing
-- etc. Web, Mobile
- ## Automate Workflow
-- Veriosn Control, Automate Code Review,  Continous Integration, Automate Deploy

---
# References:

Tdd by http://www.somkiat.cc
