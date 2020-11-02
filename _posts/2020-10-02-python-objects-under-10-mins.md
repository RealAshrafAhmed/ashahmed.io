---
layout: post
title:  "Python Objects under 10 minutes"
author: "Ashraf Ahmed"
---

In the early days of programming, all software programs were composed of variables and subroutines. Take for instance the [original Apollo 11 guidance computer source code](https://github.com/chrislgarry/Apollo-11), it contains thousands of pages of source code. Modern software is even [much larger](https://www.visualcapitalist.com/millions-lines-of-code/#:~:text=Not%20including%20backend%20code%2C%20Facebook,a%20whopping%202%20billion%20lines). Facebook alone includes approximately 61 million lines of code. Objects were invented as a way of breaking up a software program into smaller functional units. [This blog](https://medium.com/@atherlangga/retracing-original-object-oriented-programming-f8b689c4ce50) discusses the object oriented programming history.  

## What is an Object 
Everything in Python is an object. Even the literal expressions 1 and True. Below is an example of different object types 
  
```python
>>> type(1) 

<class 'int'> 

>>> type(1.0) 

<class 'float'> 

>>> type('This is a string') 

<class 'str'> 

>>> type(True) 

<class 'bool'> 

>>> type(True == False) 

<class 'bool'> 

>>> type(np.array(range(10))) 

<class 'numpy.ndarray'> 
```
 
Quickly you will notice that objects and classes are connected. Classes are like building blue prints while objects are the buildings themselves. To create an object you need to build using the blueprint. The help built-in function, gives you information about the class a given object is "instantiated" from. 

```python
>>> help(1) 

Help on int object: 

  

class int(object) 

 |  int(x=0) -> integer 

 |  int(x, base=10) -> integer 

 |   

 |  Convert a number or string to an integer, or return 0 if no arguments 

 |  are given.  If x is a number, return x.__int__().  For floating point 

 |  numbers, this truncates towards zero. 
```
 

Similarly, you can get more information about bool objects: 

  

Help on bool object: 

  
```python
>>> help(True) 

class bool(int) 

 |  bool(x) -> bool 

 |   

 |  Returns True when the argument x is true, False otherwise. 

 |  The builtins True and False are the only two instances of the class bool. 

 |  The class bool is a subclass of the class int, and cannot be subclassed. 

…etc 
```
  

You can even use help to get information about a given method in a class 

  
```python
>>> help(np.array.__sizeof__) 

  

Help on built-in function __sizeof__: 

  

__sizeof__(...) method of builtins.builtin_function_or_method instance 

    __sizeof__() -> int 

    size of object in memory, in bytes 
```
  

The dir built-in function, gives you a list of the methods and the attributes a class has. 

  
```python
>>> dir(1) 

['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__', '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__', '__float__', '__floor__', '__floordiv__', … etc] 

  

>>> dir(np.array(range(10))) 

['T', '__abs__', '__add__', '__and__', '__array__', '__array_finalize__', '__array_function__', '__array_interface__', '__array_prepare__', '__array_priority__', …] 
```
  

Clearly, this shouldn't be your main source of information but it can be very handy if you want to quickly check if a given class/object has a given method or the meaning of a method or an attribute. 

### Calling an Object method 

There are 2 ways to call methods of an object. The first is to use the dot shorthand notation: 

  
```python
>>> print("hello there!".upper()) 

HELLO THERE! 
```
  

It is very natural to do that but it doesn't exactly tell you how did that upper method exist in the first place. Another is using a functional style: 

  
```python
>>> print(str.upper("hello there!")) 

HELLO THERE! 
```
  

The functional style makes it clear that object methods are nothing but functions defined within a class scope. 

#### Mathematical and Logical operators on object methods 

It might not be clear how an expression such as 1+3 translates to objects and methods. One way to think about that expression is that we are using the integer value of the object on the left, adding to it the value of the integer on the right and returning a new integer object. The following snippet is equivalent: 

 
```python
>>> print(int.__add__(1,3)) 

4 
```
  

Which is equivalent to 

 
```python
>>> print(int(1).__add__(1)) 

2 
```
This is exactly what python does under the hood when you evaluate 1 + 3. Almost all mathematical and logical operators have equivalent hidden methods that are invoked under the hood. Another example is the value of 1 < 3. This is its equivalent: 

  
```python
>>> print(int.__lt__(1,3)) 

True 
```

There is really nothing especial about any of the shorthand operators that we use on daily basis. They are just class methods that the python interpreter knows how to translate. It is nothing but syntactical sugar. 

### More Information 
There is a lot you can do with python objects. This blog provides a simple introduction on how to create your own classes. For more advanced material, this datacamp course provide detailed information about objects and classes in Python. 