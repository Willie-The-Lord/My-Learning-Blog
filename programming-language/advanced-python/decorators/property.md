# @property

### What is @property

Python programming provides us with a built-in `@property` decorator which makes usage of getter and setters much easier in Object-Oriented Programming.

### Using Getters and Setters

```python
class Celsius:
    def __init__(self, temperature=0):
        self.set_temperature(temperature)

    def to_fahrenheit(self):
        return (self.get_temperature() * 1.8) + 32

    # getter method
    def get_temperature(self):
        return self._temperature

    # setter method
    def set_temperature(self, value):
        if value < -273.15:
            raise ValueError("Temperature below -273.15 is not possible.")
        self._temperature = value

human = Celsius(37)

human.set_temperature(-300)

print(human.to_fahrenheit())

# Output => ValueError: Temperature below -273.15 is not possible.
```

### Using Property class

```python
class Celsius:
    def __init__(self, temperature=0):
        self._temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    # getter
    def get_temperature(self):
        return self._temperature

    # setter
    def set_temperature(self, value):
        if value < -273.15:
            raise ValueError("Temperature below -273.15 is not possible")
        self._temperature = value

    # creating a property object
    temperature = property(get_temperature, set_temperature)

c = Celsius(20)
c.temperature

# Output => 20
```

### Using @property

<pre class="language-python"><code class="lang-python"><strong>class Celsius:
</strong>    def __init__(self, temperature=0):
        self.temperature = temperature

    def to_fahrenheit(self):
        return (self.temperature * 1.8) + 32

    @property
    def temperature(self):
        return self._temperature

    @temperature.setter
    def temperature(self, value):
        if value &#x3C; -273.15:
            raise ValueError("Temperature below -273 is not possible")
        self._temperature = value

human = Celsius(37)

coldest_thing = Celsius(-300)

# Output => ValueError: Temperature below -273 is not possible
</code></pre>

### Jupyter Notebook File Download

{% file src="../../../.gitbook/assets/property.ipynb" %}

### Resource

[https://www.programiz.com/python-programming/property](https://www.programiz.com/python-programming/property)
