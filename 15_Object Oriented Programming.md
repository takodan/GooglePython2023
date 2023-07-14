# Object-oriented Programming
class: is used to define idae.  
object/instance: is an instance of the class.  
attributes: are the characteristics of the class.  
methods: are functions that are part of the class.  
dot notation("."): to access methods or attributes of the class.

```python
dir() # print all the attributes and methods of an object
help() # return the documentation for the corresponding class

# define classes
class ClassName:
    classAttribute1 = ""
    classAttribute2 = "defaultValue"

nameObj = Name
nameObj.classAttribute1 = "wah"
print(nameObj.classAttribute1, nameObj.classAttribute2) # "wah defaultValue"
```
# Classes and Methods
```python
class Apple:
    # add documentation to our own classes, methods, and functions
    # this documentation call docstrings
    """this message will show when you call help(Apple)."""

    # special methods
    # def __init__(self, para)
    # this special method call constructor.
    # when you call the class, the constructor of that class is called.
    # self: represents the instance.
    def __init__(self, color, flavor):
        self.color = color
        self.flavor = flavor

    # def __str__(self)
    # when an object is passed to the print(), print the return value.
    def __str__(self):
        return "This apple is {} and its flavor is {}".format(self.color, self.flavor)

    # methods
    def method_name(self, other_parameters):
        """Documentation for the method."""
        body_of_method
```
### cheat sheet
* Classes define the behavior of all instances of a specific class.
* Each variable of a specific class is an instance or object.
* Objects can have attributes, which store information about the object.
* You can make objects do work by calling their methods.
* The first parameter of the methods (self) represents the current instance.
* Methods are just like functions, but they can only be used through a class
* Special methods start and end with __.

# Code Reuse
```python
class Animal:
    sound = ""
    def __init__(self, name):
        self.name = name
    def speak(self):
        print("I'm {name}! {sound}".format(name=self.name, sound=self.sound))

# inheritance
class Piglet(Animal):
    sound = "Oink!"

hamlet = Piglet("Hamlet")
hamlet.speak() # I'm Hamlet! Oink!

# composition
# one class makes use of code contained in another class
class Repository:
     def __init__(self):
         self.packages = {} # dictionary is also a class
     def add_package(self, packageObj): #  takes a Package object as a parameter
        # adds it to our dictionary, using the packageObj name attribute as the key
         self.packages[packageObj.name] = packageObj
     def total_size(self):
         result = 0
         for package in self.packages.values(): # valuses are packageObj
             result += package.size
         return result
```


