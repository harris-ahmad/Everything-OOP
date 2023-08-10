# Classes

- [Classes](#classes)
  - [What is a class?](#what-is-a-class)
  - [Important Terminology](#important-terminology)

## What is a class?

In C++, we have different built-in/ configured data types like `int`, `string`, `float` etc that we use to initialize variables and document the return types of functions/ methods.

An `object` can be created out of these data types. Before we dig any deeper, it is important to understand the true essence of what objects are and why you're encouraged to spend time getting your head around this particular concept. An object can be created out of any of the afforementioned data types. In simpler terms, it can be called an instance of a data type. For example, if we have a variable `int a = 5;`, we can create an object `a` out of the data type `int`. This object `a` will have all the properties of the data type `int` and can be used to perform operations on it.

How exciting would it be if you could create your own data types? Well, you can! This is where classes come in. A class is a user-defined data type that can be used to create objects. A class is a **blueprint** for an object. It defines what *properties* and *methods* an object of that class will have. For example, if we want to create a class `Person`, we can define the properties of a person like `name`, `age`, `gender` etc. and the methods like `walk()`, `talk()`, `eat()` etc. that a person can perform. Once we have defined the class, we can **create objects** of that class. For example, we can create an object `person1` of the class `Person` and assign values to its properties like `person1.name = "John"`, `person1.age = 25` etc. and call its methods like `person1.walk()`, `person1.talk()` etc.

In simpler terms, classes are used to create user-defined data types. You'll be amazed to know that these configured data types in C++ (`int`, `float`, etc) are classes themselves. They are just pre-defined classes that come with the C++ compiler. You can create your own classes and use them to create objects.

The cool thing is that our class can contain multiple variables, pointers, dynamic memory allocation, functions, etc. We'll be covering all of these in the upcoming sections.

Let's start off with a simple example of a **person** class and create objects of that class.

We can see that the attributes of the person class would be:

**Data Menbers:**
- name
- age
- gender
- height

**Member Functions:**
- walk()
- talk()
- eat()

Woah! A whole lot of challenging terms. Let's break them down one by one.

## Important Terminology

**Data Members:** These are the variables that are used to store the data of the object. In our case, the data members would be `name`, `age`, `gender` and `height`. These are the properties of a person. We can also call them **attributes** of a person.

**Member Functions:** These are the functions that are used to perform operations on the data members. In our case, the member functions would be `walk()`, `talk()` and `eat()`. These are the actions that a person can perform. We can also call them **methods** of a person.

**Object:** An object is an instance of a class. For example, if we have a class `Person`, we can create an object `person1` of that class. This object `person1` will have all the properties and methods of the class `Person`. We can also call it an instance of the class `Person`.