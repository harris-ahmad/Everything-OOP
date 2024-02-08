# Constructors 

- [Constructors](#constructors)
  - [What is a Constructor?](#what-is-a-constructor)
    - [Default Constructor](#default-constructor)
    - [Parameterized Constructors](#parameterized-constructors)
    - [Copy Constructor](#copy-constructor)
  - [this Pointer](#this-pointer)

## What is a Constructor?

As the name implies, a constructor is a method that is used to construct an object. It is called when an object of a class is created. Just how an algorithm can be thought of as a list of steps, a constructor can be thought of as a list of steps that are executed when an object is created.

> It is crucial to take note that a constuctor's name must be the same as the class name and it does not have a return type.

There are three types of constructors:
- Default Constructor
- Parameterized Constructor
- Copy Constructor

### Default Constructor

A default constructor is a constructor that takes no parameters. It is called when an object is created without any arguments. 
We have a `Date` class that stores the day, month and year of a date. We can create a constructor that takes in the day, month and year as parameters and sets the values of the instance variables accordingly.

```cpp
class Date {
  private:
    int day;
    int month;
    int year;
  public:
    Date();
    void printDate();
};

Date::Date() {
  day = 1;
  month = 1;
  year = 2000;
}

void Date::printDate() {
  cout << day << "/" << month << "/" << year << endl;
}
```

Okay, okay, I know what you're thinking. "Why do we need a constructor when we can just set the values of the instance variables in the `main()` function?" Well, you're right. We can do that. But what if we have a class that has 10 instance variables? It would be a pain to set the values of all 10 instance variables in the `main()` function. This is where constructors come in handy. We can just create a constructor that takes in 10 parameters and sets the values of the instance variables accordingly. 

How do we create an object of the `Date` class? We can create an object of the `Date` class by calling the constructor of the `Date` class. 

```cpp
int main() {
  Date d1; // yes, it is this simple
  d1.printDate(); // 1/1/2000
  return 0;
}
```

I know what's going through your mind right now. "But what if I don't want to set the values of all 10 instance variables? What if I only want to set the values of 5 instance variables?" Well, you can create multiple constructors that take in different parameters. We call such constructors **parameterized constructors**. How are they different from setters? Well, setters are methods that set the values of instance variables after the object has been created. Parameterized constructors are methods that set the values of instance variables when the object is created.

### Parameterized Constructors

We use parameterized constructors to override the values initialized by the default constructor and give preference to the values passed as arguments. 

```cpp
class Date {
  private:
    int day;
    int month;
    int year;
  public:
    Date();
    Date(int d, int m, int y);
    void printDate();
};

Date::Date() {
  day = 1;
  month = 1;
  year = 2000;
}

Date::Date(int d, int m, int y) {
  day = d;
  month = m;
  year = y;
}

void Date::printDate() {
  cout << day << "/" << month << "/" << year << endl;
}

int main() {
  Date d1;
  Date d2(2, 2, 2002);
  d1.printDate(); // 1/1/2000
  d2.printDate(); // 2/2/2002
  return 0;
}
```

**Note:** Did you observe how we called the parameterized constructor? We passed the values of the day, month and year as arguments to the constructor in the second line of the `main()` function.

### Copy Constructor

A copy constructor is used to create a new object as a copy of an existing object. It is called when an object is created from another object of the same class. It's most commonly used when we want to pass an object to a function by value. 

```cpp
class Date {
  private:
    int day;
    int month;
    int year;
  public:
    Date();
    Date(int d, int m, int y);
    Date(const Date &obj);
    void printDate();
};

Date::Date() {
  day = 1;
  month = 1;
  year = 2000;
}

Date::Date(int d, int m, int y) {
  day = d;
  month = m;
  year = y;
}

Date::Date(const Date &obj) {
  day = obj.day;
  month = obj.month;
  year = obj.year;
}

void Date::printDate() {
  cout << day << "/" << month << "/" << year << endl;
}

int main() {
  Date d1(1, 1, 2001);
  Date d2(d1); // copy constructor
  d1.printDate(); // 1/1/2001
  d2.printDate(); // 1/1/2001
  return 0;
}
```

**Note:** Did you observe how we called the copy constructor? We passed the object `d1` as an argument to the constructor in the second line of the `main()` function.

There's another way of calling the copy constructor. We can call the copy constructor by setting the value of an object to another object.

```cpp
int main() {
  Date d1(1, 1, 2001);
  Date d2 = d1; // copy constructor
  d1.printDate(); // 1/1/2001
  d2.printDate(); // 1/1/2001
  return 0;
}
```
Questions, right? Why do we need a copy constructor when we can just set the value of an object to another object? Well, the copy constructor is called when we pass an object to a function by value. Let's say we have a function that takes in a `Date` object as a parameter. If we pass an object to the function, the copy constructor is called. If we set the value of an object to another object, the copy constructor is not called. 

```cpp
void printDate(Date d) {
  d.printDate();
}

int main() {
  Date d1(1, 1, 2001);
  Date d2 = d1; // copy constructor
  printDate(d1); // copy constructor
  return 0;
}
```
What would have happened if we didn't have a copy constructor? The values of the instance variables of the object `d1` would have been copied to the object `d` in the `printDate()` function. But the object `d` would have been destroyed after the function call. So, the values of the instance variables of the object `d` would have been lost. This is why we need a copy constructor. It creates a copy of the object that is passed to the function.

Sometimes, the names of the parameters of the copy constructor are the same as the names of the instance variables. In such cases, we use the `this` pointer to distinguish between the instance variables and the parameters. 

## this Pointer

The `this` pointer is a pointer that points to the object that invokes the member function. It is used to refer to the current object. It is used to access the instance variables of the current object. 

```cpp
class Date {
  private:
    int day;
    int month;
    int year;
  public:
    Date();
    Date(int day, int month, int year);
    Date(const Date &obj);
    void printDate();
};

Date::Date() {
  this->day = 1;
  this->month = 1;
  this->year = 2000;
}

Date::Date(int day, int month, int year) {
  this->day = day;
  this->month = month;
  this->year = year;
}

Date::Date(const Date &obj) {
  this->day = obj.day;
  this->month = obj.month;
  this->year = obj.year;
}

void Date::printDate() {
  cout << this->day << "/" << this->month << "/" << this->year << endl;
}
```

But why do we need the `this` pointer? Why can't we just use the names of the instance variables? Well, we can. But it is a good practice to use the `this` pointer. It makes the code more readable. It makes it easier to distinguish between the instance variables and the parameters. It's not always easy to come up with alternate names for the parameters since there's an inherent trade-off between readability and brevity. 

Great! We have learnt about constructors. But what if we want to destroy an object? What if we want to free up the memory that was allocated to the object? We can do that by using destructors. Let's learn about destructors in the next chapter.