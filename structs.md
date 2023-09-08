# Structs

- [Structs](#structs)
  - [A gentle introduction to Structs](#a-gentle-introduction-to-structs)
  - [Declaring, Initializing and Accessing structs in the `main()` function.](#declaring-initializing-and-accessing-structs-in-the-main-function)
  - [Structs and Arrays](#structs-and-arrays)
  - [Struct of Structs - Say Hello to Nesting](#struct-of-structs---say-hello-to-nesting)

## A gentle introduction to Structs

Structs are a way to group variables together to form a single data type. They are similar to classes in the sense that they can also contain variables and functions. The only difference is that structs are public by default whereas classes are private by default.
We'll be covering classes in the upcoming sections. For now, let's understand what structs are and how they are used in C++.

Before we get to how we declare and use structs in our programs, it's important that we build some intuition about them. Struct stands for structure. It is a way to group variables together to form a single data type. But why do we need to group variables and package them in a container-like structure? Well, let's consider a simple example. Suppose we want to store the details of a student. We can do so by creating variables for each of the details. For example, we can create a variable `name` to store the name of the student, a variable `age` to store the age of the student, a variable `height` to store the height of the student, and so on. But what if we want to store the details of multiple students? We can create multiple variables for each of the details of each of the students. But this is not a good idea. It's not scalable, efficient or maintainable. 

This is where structs come into play. We can create a struct called `Student` and store all the details of a student in it. We can then create multiple variables of the `Student` type to store the details of multiple students. This is a much better approach. I know, I know you're excited to see some code. Let's get to it.

```cpp

struct Student {
    string name; // name of the student
    int age; // age of the student
    float height; // height of the student
};

```

## Declaring, Initializing and Accessing structs in the `main()` function.

We can see that we have created a struct `Student` and defined its data members. These data members are the variables that we want to store in the struct. We can create a variable of the `Student` type and store the details of a student in it. Let's see how we can do that. Since the struct is public by default, we can access its data members directly. Don't worry if the keyword *Struct* sounds alien to you right now. Wait until you cover public, private and protected access modifiers. It'll all make sense.

```cpp
struct Student {...} // omitted for brevity

int main() {
    Student s1;
    s1.name = "John";
    s1.age = 21;
    s1.height = 5.8;

    cout << s1.name << endl; // John
    cout << s1.age << endl; // 21
    cout << s1.height << endl; // 5.8
}

```

We can see that we have created a variable `s1` of the `Student` type and stored the details of a student in it. We can access the data members of the struct using the dot (`.`) operator. Can we skip to the good stuff now? Yes, we can. Let's see how we can create an array of structs. We can create an array of structs just like we create an array of any other data type. Let's see how we can do that.

## Structs and Arrays 

```cpp

struct Student {...} // omitted for brevity

int main() {
    Student s[3];
    s[0].name = "John";
    s[0].age = 21;
    s[0].height = 5.8;

    s[1].name = "Jane";
    s[1].age = 20;
    s[1].height = 5.5;

    s[2].name = "Jack";
    s[2].age = 22;
    s[2].height = 5.9;

    for (int i = 0; i < 3; i++) {
        cout << s[i].name << endl;
        cout << s[i].age << endl;
        cout << s[i].height << endl;
        cout << "----" << endl;
    }

    /*
    Output:

    John
    21
    5.8
    ----
    Jane
    20
    5.5
    ----
    Jack
    22
    5.9
    ----
    */
}
```

We can see that we have created an array of structs and stored the details of multiple students in it. We can access the data members of the struct using the dot (`.`) operator. We can also use a for loop to iterate over the array of structs and print the details of each student. Still don't find the concept *edgy* and cool? What would happen if we created a struct of structs? Is that even possible?

## Struct of Structs - Say Hello to Nesting 

```cpp

struct Address {
    string street;
    string city;
    string state;
    int zipCode;
};

struct Student {
    string name;
    int age;
    Address address; // struct of structs
    float height;
};

int main() {
    Student s1;
    s1.name = "John";
    s1.age = 21;
    s1.address.street = "123 Main St";
    s1.address.city = "New York";
    s1.address.state = "NY";
    s1.address.zipCode = 10001;
    s1.height = 5.8;

    cout << s1.name << endl; // John
    cout << s1.age << endl; // 21
    cout << s1.address.street << endl; // 123 Main St
    cout << s1.address.city << endl; // New York
    cout << s1.address.state << endl; // NY
    cout << s1.address.zipCode << endl; // 10001
    cout << s1.height << endl; // 5.8
}

```

What about struct of structs of structs? Is that possible? Yes, it is. You can create a struct of structs of structs and so on. You can create as many levels of nesting as you want.

Strictly in OOP terminology, you've studied something known as **composition**.