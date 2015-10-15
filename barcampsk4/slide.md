class: center, middle

#TDD เปลี่ยนชีวิตคนคนนี้ยังไง
###@ibotdotout

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
  # Arrange
  score = 81

  # ACT
  grade = cut_grade(score)

  # Assert
  self.assertEqual('A', grade)

def test_score_70_get_B(self):
  score = 70
  grade = cut_grade(score)
  self.assertEqual('B', grade)

def test_score_49_get_F(self):
  score = 49
  grade = cut_grade(score)
  self.assertEqual('F', grade)
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
  self.assertEqual('F', grade)
```

---

class: center, middle
# Befefit & Wrong Mindset of Testing

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
# Wrong Mindset of Testing

## Make it work, (write) Test Later
-- Technique debt. You pay what you play.
## Small project don't write test !!!
-- Every code should have test.  
-- Testcase is your document.  
-- Try in small project then appiled in real-world project later.

---
class: center, middle
# Test Driven = (Write) Test first

---

# TDD Life Cycle

.right[![](https://leantesting.com/resources/wp-content/uploads/2015/02/tdd-circle-of-life.png)]

1. Add testcase
2. Look test fail
3. Write Code
4. Run tests
5. Refactor

---

# TDD - Divide and Conquer

Q: Calculate area under curve ?  
A: Cut into small piece and calculate area than sum all area.
Benefits

.right[![](http://i.ytimg.com/vi/JbEbhv8ybmE/hqdefault.jpg)]

- Small Task
- Focus
- Progress
- No fear
- Achievements

---

class: center, middle
# Live Demo (Unittest)

---

class: center, middle
# Test First vs Test Later
Test -> Code or Code -> Test

---

# Why test first

<iframe width="720" height="480"
src="https://www.youtube.com/embed/dYim_QZqppY" frameborder="0"
allowfullscreen></iframe>

---

# Why test first (Cont.)

- ## Think What not How ?
-- Think What it does, not how it implement.
- ## Focus on your task and Prevent Over Design
-- Do The Simplest Thing That Could Possibly Work #DTSTTCPW
- ## Make Testable Code.
-- Not every code that easy to test.

---

# What wrong with test later?

- ## Hard to test
-- Your code not design to be testable.
- ## Your task done, why not rest ?
-- Your never comeback to write test.
- ## Write test to passed your code. What !!!
-- You should write code to passed your test.

---
class: center, middle
# Wrong Mindset of TDD

---

# Wrong Minset of TDD
## Make your work slow
-- You can drive faster because of break.
## Don't have to design

---

class: center, middle
# How to start TDD

---

# Choose your weapon

- Java - jUnit
- Cpp - CppUnit
- C#  - nUnit
- PHP - PHPunit
- Pyhon - unittest *
- Ruby - Rspec *
- Go - Testing *

---

# Pratices in TDD


---

# Testing/TDD in real-world project

---

class: center, middle
# Next ?

---
- #Testing
- ## Integration Testing
-- etc. Database, Third party librairy
- ## UI Testing
-- etc. Web, Mobile

---
- #Automate Workflow
-- Veriosn Control
-- Automate Code Review
-- Continous Integration
-- Automate Deploy

---

class: center, middle
# Demo

---
# References:
- [All About Testing by ibot.out]()
- [Tdd by somkiat.cc](http://www.somkiat.cc/tag/tdd/)
- [Tdd by Sansarun Sukawongviwat @barcampsk#3](https://docs.google.com/presentation/d/1WvtMy0etIthiriuQngOLdSpzOyV-YRLwZA5cqEfKQEI/edit#slide=id.p)
- [TDD ง่ายๆ สั้นๆ (Java)](https://www.youtube.com/watch?v=9OQeO64x-2k)
- [Coding Dojo - TDD - Lesson 1 (Java)](https://www.youtube.com/watch?v=4UM73byPFlA)
- [Understanding Test Driven Development](https://www.youtube.com/watch?v=q5Xd1tmIgec)
- [automated-test by somkiat.cc](http://www.somkiat.cc/tag/automated-test/)
- [“วิธีการเรียนรู้/การเริ่มต้นงาน”: Trick ง่ายๆ ที่หลายคนมองข้าม](http://www.rawitat.com/2014/10/01/1847/#more-1847)
- [Technical Debt มันคืออะไร ?](http://www.somkiat.cc/what-is-technical-debt/)
