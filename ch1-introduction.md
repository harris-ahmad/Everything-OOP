# Classes

- [Classes](#classes)
  - [What is a class?](#what-is-a-class)

## What is a class?

In C++, we have different built-in/ configured data types like `int`, `string`, `float` etc that we use to initialize variables and document the return types of functions/ methods.

An `object` can be created out of these data types. Before we dig any deeper, it is important to understand the true essence of what objects are and why you're encouraged to spend time getting your head around this particular concept. An object can be created out of any of the afforementioned data types. In simpler terms, it can be called an instance of a data type. For example, if we have a variable `int a = 5;`, we can create an object `a` out of the data type `int`. This object `a` will have all the properties of the data type `int` and can be used to perform operations on it.

How exciting would it be if you could create your own data types? Well, you can! This is where classes come in. A class is a user-defined data type that can be used to create objects. A class is a **blueprint** for an object. It defines what *properties* and *methods* an object of that class will have. For example, if we want to create a class `Person`, we can define the properties of a person like `name`, `age`, `gender` etc. and the methods like `walk()`, `talk()`, `eat()` etc. that a person can perform. Once we have defined the class, we can **create objects** of that class. For example, we can create an object `person1` of the class `Person` and assign values to its properties like `person1.name = "John"`, `person1.age = 25` etc. and call its methods like `person1.walk()`, `person1.talk()` etc.

In simpler terms, classes are used to create user-defined data types. You'll be amazed to know that these configured data types in C++ (`int`, `float`, etc) are classes themselves. They are just pre-defined classes that come with the C++ compiler. You can create your own classes and use them to create objects.