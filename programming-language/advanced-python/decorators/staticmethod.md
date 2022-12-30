# @staticmethod

### What is a static method?

Static methods, much like [class methods](https://www.programiz.com/python-programming/methods/built-in/classmethod), are methods that are bound to a class rather than its object.

They do not require a class instance creation. So, they are not dependent on the state of the object.

The difference between a static method and a class method is:

* Static method knows nothing about the class and just deals with the parameters.
* Class method works with the class since its parameter is always the class itself.

```python
class Calculator:
    def add(num1, num2):
        return num1 + num2
    
Calculator.add_numbers = staticmethod(Calculator.add)
print(Calculator.add_numbers(1, 2))

# Output => 3
```

### Syntax

```python
staticmethod(function)
```

{% hint style="info" %}
Static method knows nothing about the class and just deals with the parameters.
{% endhint %}

### How to call

<pre><code># called by the class
<strong>Class.staticmethod()
</strong><strong>
</strong># called by its object
Class().staticmethod()
</code></pre>

### Create a utility function as a static method

```python
class Dates:
    def __init__(self, date):
        self.date = date
        
    def getDate(self):
        return self.date

    @staticmethod
    def toDashDate(date):
        return date.replace("/", "-")

date = Dates("04-12-202")
other_date = "04/12/2022"
print(Dates.toDashDate(other_date))

# Output => 04-12-2022
```

### Having a single implementation

```python
class Dates:
    def __init__(self, date):
        self.date = date
        
    def getDate(self):
        return self.date

    @staticmethod
    def toDashDate(date):
        return date.replace("/", "-")

class DatesWithSlashes(Dates):
    def getDate(self):
        return Dates.toDashDate(self.date)

date = Dates("12-04-2022")
dateFromDB = DatesWithSlashes("12/04/2022")

print(isinstance(dateFromDB, DatesWithSlashes))

if(date.getDate() == dateFromDB.getDate()):
    print("Equal")
else:
    print("Unequal")

# Output =>
# True
# Equal
```

### Jupyter Notebook File Download

{% file src="../../../.gitbook/assets/staticmethod.ipynb" %}

### Resource

[https://www.programiz.com/python-programming/methods/built-in/staticmethod](https://www.programiz.com/python-programming/methods/built-in/staticmethod)
