# Classes

- [Classes](#classes)
  - [What is a class?](#what-is-a-class)
  - [Important Terminology](#important-terminology)
  - [Why use classes?](#why-use-classes)
  - [Access Modifiers](#access-modifiers)
    - [Private Access Modifier](#private-access-modifier)
    - [Public Access Modifier](#public-access-modifier)
    - [Protected Access Modifer](#protected-access-modifer)

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

## Why use classes?

Object Oriented Paradigm isn't restricted to C++ only. It is a programming paradigm that is used in many programming languages like Java, Python, C#, etc. It is a very powerful paradigm that allows us to create complex programs with ease. It is a very important concept to understand and master. It is used in many real-world applications. For example, if you're creating a game, you can create a class `Player` and create objects of that class to represent the players in the game. If you're creating a banking application, you can create a class `Account` and create objects of that class to represent the accounts of the customers. If you're creating a social media application, you can create a class `User` and create objects of that class to represent the users of the application. The possibilities are endless. You can create as many objects of a class as you want. You can also create multiple classes in a single program. You can also create objects of one class inside another class. We'll be covering all of these concepts in the upcoming sections.

In essence, classes help you compartmentalize the code of an application. Different components would become separate classes which would interact through interfaces. The most significant advantage of using classes is the usability of the code. You can create objects of a class and use them in different parts of the program. Not only that, you can even *import* these classes in other programs and use them there. This is the power of classes.

The question is, how do you define a class in a program? Let's demonstrate this with C++ code.

```cpp
class ClassName {
  // define
}
```

## Access Modifiers

There are three types of access modifiers in C++: `public`, `private` and `public`. We can use these access modifiers to define the `scope` of our data members and member functions. The question that you might have is why do we need to define the scope of our data members and member functions or why do we need access modifiers in the first place? Before we get to that, let's understand what `scope` means. 

**Scope:** Scope refers to the visibility of a variable or a function. In other words, it refers to the part of the program where a variable or a function can be accessed. For example, if we define a variable `int a = 5;` inside a function `main()`, we can only access it inside the `main()` function. If we try to access it outside the `main()` function, we'll get an error. This is because the scope of the variable `a` is limited to the `main()` function. We can also call it a `local` variable. On the other hand, if we define a variable `int a = 5;` outside the `main()` function, we can access it anywhere in the program. We can also call it a `global` variable. The scope of a global variable is the entire program. Woah! That's a mouthful of words. Nothing to worry, we will dig deeper into these concepts in the upcoming chapters.

### Private Access Modifier

In C++ or other programming languages like Java, we can impose restrictions on different data members outside the class. The goal, on a broader level, is to keep the data members private since we don't want the users of our application manipulating the data directly without an **interface.** By default, all data members are private in C++ while they are public in Python. Wow! We're promoting security. The question is, how do we make our data secure? In other words, how do I make my data members private?

Let's demonstrate this using a simple example in C++.

```cpp
class Class1 {
  int num; // this is by default a private member
}

class Class2 {
  private: // we have explicitly defined that whatever variables lie in this indented block would be private and cannot be accessed directly in the main() function.
    int num;
}
```

We can make our data members private using the `private` keyword followed by a colon (`:`). 

### Public Access Modifier

We can also make our data members public using the `public` keyword followed by a colon (`:`). This means that the data members can be accessed directly in the `main()` function. Strictly, in the OOP terminology, it implies that the data members are accessible outside the class. Let's demonstrate this using a simple example in C++. It's important to understand that the member functions are usually public unless we explicitly define them as private. Before we get to how we declare member functions, let's recall what member functions are. 

**Member Functions:** These are the functions that are used to perform **operations** on the data members. We access both the private and public data members using member functions. Synonymously, these member functions are also called **methods** of a class. Now back to what the public access modifier is and how do we define it in a programming langauge like C++. 

```cpp
class Class1 {

  private:
    int num2; // private data member

    void print2() { // private member function
      cout << num2 << endl;
    }

  public:
    int num; // publicly declared data member

    void print() { // publicly declared member function
      cout << num << endl;
    }
}

int main() {
  Class1 c;
  c.num = 3; 
  c.print(); // 3

  c.num2 = 4; // error: 'int Class1::num2' is private within this context
  c.print2(); // error: 'void Class1::print2()' is private within this context

  cout << c.num << endl; // 3
}
```

### Protected Access Modifer

