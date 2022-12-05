# @classmethod

### What is classmethod()

The `classmethod()` method returns a class method for the given function.

```python
class Athlete:
    total_score = 0
    
    def earn_score(self, points):
        total_score = points
        print("My Total Score: ", total_score)

# convert earn_score() to class method
Athlete.print_score = classmethod(Athlete.earn_score)
Athlete.print_score(100) 

# Output => My Total Score:  100      
```

### Syntax

```python
classmethod(function)
```

### How to call

```
# called by the class
Class.classmethod()

# called by its object
Class().classmethod()
```

{% hint style="info" %}
Always attached to a class with the first argument: class itself cls

```python
def classMethod(cls, args...)
```
{% endhint %}

### Create class method using @classmethod

```python
class Athlete:
    total_score = 100
    
    @classmethod
    def print_score(cls):
        print("My Total Score: ", cls.total_score)

Athlete.print_score()

# Output => My Total Score:  100
```

### Create factory method using class method

```python
from datetime import date

class Athlete:
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    @classmethod
    def calculateAge(cls, name, birth_year):
        return cls(name, date.today().year - birth_year)

    def display(self):
        print(self.name + "'s age is: " + str(self.age))
        
athlete1 = Athlete('Perry', 20)
athlete1.display()

# equivalent to Athlete(name, date.today().year - birthYear)
athlete2 = Athlete.calculateAge('Willie', 1999)
athlete2.display()

# Output => 
# Perry's age is: 20
# Willie's age is: 23
```

### Correct instance creation in inheritance

```python
from datetime import date

class Athlete:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    # Hardcode the instance type during creation
    # Cause a problem when inheriting Athlete to Student
    @staticmethod
    def calculateFromFathersAge(name, fatherAge, fatherPersonAgeDiff):
        return Athlete(name, date.today().year - fatherAge + fatherPersonAgeDiff)

    @classmethod
    def calculateAge(cls, name, birth_year):
        return cls(name, date.today().year - birth_year)

    def display(self):
        print(self.name + "'s age is: " + str(self.age))

class Student(Athlete):
    sex = 'Male'

# Using classmethod to ensure the OOP
s1 = Student.calculateAge('Perry', 1999)
print(isinstance(s1, Student))

s2 = Student.calculateFromFathersAge('Willie', 1965, 20)
print(isinstance(s2, Student))

# Output => 
# True
# False
```

### Jupyter Notebook File Download

{% file src="../../../.gitbook/assets/classmethod.ipynb" %}

### Resource

[https://www.programiz.com/python-programming/methods/built-in/classmethod](https://www.programiz.com/python-programming/methods/built-in/classmethod)
