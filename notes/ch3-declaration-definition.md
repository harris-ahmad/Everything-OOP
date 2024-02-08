# Declaring and Defining Member Functions

- [Declaring and Defining Member Functions](#declaring-and-defining-member-functions)
  - [How do we declare member functions?](#how-do-we-declare-member-functions)
  - [Scope Resolution Operator (::)](#scope-resolution-operator-)
  - [Setters and Getters](#setters-and-getters)

## How do we declare member functions?

Like all functions, member function can either be defined directly inside the class or declared in the class and then defined outside the class. Member functions that are defined inside the class are implicitly inline. We'll be covering inline functions in the upcoming sections. For now, it is important to understand that *inline functions are faster than normal functions*. This is because the compiler replaces the function call with the actual function code. This saves the overhead of calling the function. You do not need to worry about this right now.

Here's an example:

```cpp
class Rectangle {
    private:
        int length, width;

    public:
        void setLength(int length_) {
            length = length_;
        }

        void setWidth(int width_) {
            width = width_;
        }

        int getArea() {
            return length * width;
        }
};
```

The member functions `setLength()`, `setWidth()` and `getArea()` are defined inside the class. They are implicitly inline. We can also define them outside the class. This is where the the concept of *scope resolution operator* comes into play.

## Scope Resolution Operator (::)

This operator allows us to first declare the member function in the class and then define it elsewhere in the program. This is useful when we have a lot of member functions. It makes the code more readable and maintainable. Here's an example:

```cpp
class Rectangle {
    private:
        int length, width;

    public:
        void setLength(int length_);
        void setWidth(int width_);
        int getArea();
};

void Rectangle::setLength(int length_) {
    length = length_;
}

void Rectangle::setWidth(int width_) {
    width = width_;
}

int Rectangle::getArea() {
    return length * width;
}
```

Wait, what? What is this sorcery? How did we define the member functions outside the class? Well, it's not that complicated. We use the scope resolution operator (`::`) to define the member functions outside the class. The syntax is as follows:

```cpp
<return_type> <class_name>::<member_function_name>(<parameters>) {
    // function body
}
```

The `<return_type>` is the data type of the value that the function returns. The `<class_name>` is the name of the class to which the member function belongs. The `<member_function_name>` is the name of the member function. The `<parameters>` are the parameters that the member function takes. The function body is the code that is executed when the function is called.

The question that still arises is why do we need to define the member functions outside the class? Well, it's not necessary. It's just a good practice. It makes the code more readable and maintainable. It also makes the code more modular. We can define the member functions in a separate file and then include that file in our program. This is called **separation of concerns**. We'll be covering this in the upcoming sections. For now, it is important to understand that *member functions can either be defined inside the class or outside the class*.

So far we have seen how member functions can be used to manipulate the data members. We have also seen how member functions can be used to perform operations on the data members. But, how do we access the data members? How do we access the member functions? How do you retrieve the value of the `age` data member? To answer these questions, we'll dive into the so-called **Setters and Getters**

## Setters and Getters

Setters and Getters are member functions that are used to set and get the value of a data member respectively. They are also called **accessor functions**. They are used to access the private data members of a class. They are defined using the public access modifier. The common convention is to name the setter functions as `set<DataMemberName>()` and the getter functions as `get<DataMemberName>()`. We have already seen how setter functions are defined. The following is a demonstration of how getter functions are defined:

```cpp
class Student {
    private:
        int age;

    public:
        void setAge(int age_);
        int getAge();
};

// setter function
void Student::setAge(int age_) {
    age = age_;
}

// getter function
int Student::getAge() {
    return age;
}
```
