# Classes

- [Classes](#classes)
  - [What is a Class?](#what-is-a-class)
  - [Important Terminology](#important-terminology)
  - [Why Use Classes?](#why-use-classes)
  - [Access Modifiers](#access-modifiers)
    - [Private Access Modifier](#private-access-modifier)
    - [Public Access Modifier](#public-access-modifier)
    - [Protected Access Modifier](#protected-access-modifier)

## What is a Class?

In C++, as in many other programming languages, we work with various built-in data types like `int`, `string`, and `float` to define variables and specify return types for functions. From these data types, we can instantiate objects, which are essentially instances of these types. Consider an object as a concrete manifestation of a data type; for example, given `int a = 5;`, the variable `a` is an object of the data type `int`, embodying all its properties and capable of performing operations defined for integers.

Imagine the power of defining your own data types. This is where the concept of classes comes into play. A class is a user-defined blueprint from which objects are created. It specifies the properties (attributes) and behaviors (methods) that objects of the class will possess and perform. For instance, a `Person` class might include attributes like `name`, `age`, `gender`, and methods such as `walk()`, `talk()`, `eat()`. By defining a class, you set the stage for creating objects that embody the defined structure and functionality.

Classes, therefore, allow for the creation of user-defined data types, extending the capabilities of C++ beyond its pre-defined classes (i.e., the built-in data types). With classes, you can encapsulate complex structures and behaviors, making your code more modular and reusable.

### A Simple Example: The Person Class

Consider a class representing a person. Its attributes might include:

**Data Members:**
- name
- age
- gender
- height

**Member Functions:**
- walk()
- talk()
- eat()

Through this simple model, we begin to see how classes serve as templates for creating objects with specific properties and behaviors.

## Important Terminology

- **Data Members**: Variables within a class that store the object's data. For the `Person` class, these would be `name`, `age`, `gender`, and `height`.
- **Member Functions**: Functions within a class used to operate on the object's data. In our `Person` example, these include `walk()`, `talk()`, and `eat()`.
- **Object**: An instance of a class, embodying the attributes and methods defined by the class. For instance, `person1` could be an object of the `Person` class.

## Why Use Classes?

Object-Oriented Programming (OOP) is a powerful paradigm used across various languages (Java, Python, C#, etc.) to build complex and scalable software systems. Classes offer a way to model real-world entities and their interactions, making code more modular, reusable, and easier to maintain. Whether it's a game (with `Player` classes), a banking application (with `Account` classes), or a social media platform (with `User` classes), classes help organize and structure your code, providing a clear framework for development.

## Access Modifiers

Access modifiers in C++ (`public`, `private`, `protected`) control the scope and accessibility of class members. They play a crucial role in implementing encapsulation, one of the core principles of OOP.

### Private Access Modifier

The `private` keyword restricts access to class members, making them accessible only within the class itself. This encapsulation ensures that an object's data is hidden from external manipulation, promoting security and integrity.

```cpp
class Class1 {
  private:
    int num; // Private member, accessible only within Class1
};
```

### Public Access Modifier

The `public` keyword allows class members to be accessible from outside the class, enabling interaction with an object's properties and behaviors.

```cpp
class Class1 {
  public:
    int num; // Public member, accessible from outside Class1

    void print() {
      cout << num << endl;
    }
};
```

### Protected Access Modifier

The `protected` keyword is similar to `private`, but it allows derived classes to access the protected members of their base class. This modifier is particularly useful in inheritance scenarios.

```cpp
class BaseClass {
  protected:
    int num; // Protected member, accessible in derived classes
};

class DerivedClass : public BaseClass {
  public:
    void print() {
      cout << num << endl; // Accessing

 protected member from the base class
    }
};
```

By carefully selecting access modifiers, you can control how class members are exposed and ensure that your objects maintain a well-defined interface to the rest of your program.