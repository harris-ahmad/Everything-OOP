# Destructors

- [Destructors](#destructors)
  - [What is a Destructor?](#what-is-a-destructor)
  - [Garbage Collection using Destructors](#garbage-collection-using-destructors)

## What is a Destructor?

A destructor is a special member function that is called when the lifetime of an object ends. The purpose of the destructor is to free the resources that the object may have acquired during its lifetime. For example, if an object has acquired a file handle, a network connection, or a database connection, the destructor is the place to close those handles or connections. It is worth noting that if a class does not defined a destructor explicitly, the compiler will generate one implicitly. The implicitly generated destructor will not do anything, but it will be called when the object goes out of scope. 

Woah, the jargon is strong with this one. Let's break it down.

Assuming you're **fully aware** of how dynamic memory allocation works, you know that when you allocate memory using `new`, you have to free it using `delete`. If you don't, you'll have a memory leak. This is because the memory you allocated is not automatically freed when the object goes out of scope. This is where the destructor comes in. You can use the destructor to free the memory you allocated. Unlike other programming languages like `Java` or `Python`, C++ does not have a garbage collector. This means that you have to manually free the memory you allocated.

I want you to stop reading for a second and think about the high level concept of a destructor. What do you think it is? What do you think it does? What do you think it's used for? If you're not sure, that's okay. I'll explain it to you.

A destructor specifies all additional operations which need to be performed when a class objected is deleted. For example, if a class needs to open a file upon creation, it should close the file upon deletion. If a class needs to allocate memory upon creation, it should deallocate the memory upon deletion.

> In C++, destructors are defined using the same syntax as constructors, except that they are preceded by a tilde (`~`) character. For example, the destructor for the `MyClass` class would be declared as `~MyClass()`.

Before we dive into how destructors are used or implemented in code, let's reflect on **garbage collection**. Garbage collection is a form of automatic memory management. The garbage collector, or GC, attempts to reclaim memory that is no longer being used by the program. This is done by searching for objects in memory that are no longer referenced by the program. If an object is no longer referenced, it is assumed that the object is no longer needed and the memory occupied by the object can be reclaimed. This is a very high level explanation of how garbage collection works. If you want to learn more about garbage collection, I recommend reading [this](https://en.wikibooks.org/wiki/C%2B%2B_Programming/Compiler/Linker/Libraries/Garbage_Collection) article.

## Garbage Collection using Destructors

Let's take a look at an example of how destructors are used to implement garbage collection. 

```cpp
class Collector {
  private:
    int *list;
    int size;
    int cap;

  public:
    Collector();
    Collector(int cap);
    ~Collector(); // Destructor
    bool append(int data);
    void dump();
};

Collector::Collector() {
  this->list = nullptr;
  this->size = 0;
  this->cap = 0;
}

Collector::Collector(int cap) {
  this->list = new int[cap];
  this->size = 0;
  this->cap = cap;
}

Collector::~Collector() {
  cout << "Destructor called" << endl;
  if (this->cap > 0) {
    delete[] this->list;
  }
}

bool Collector::append(int data) {
  if (this->size == this->cap) {
    return false;
  }
  this->list[this->size] = data;
  this->size++;
  return true;
}

void Collector::dump() {
  for (int i = 0; i < this->size; i++) {
    cout << this->list[i] << " ";
  }
  cout << endl;
}

int main() {
  Collector c(10);
    for (int i = 0; i < 10; i++) {
        if (!c.append(i)) { // error handling
            cout << "append failed on value " << i << "\n";
        }
    }
    c.dump();

  return 0;
}
```

**Explanation of the code:**

- The `Collector` class is a simple class that stores a list of integers. The `Collector` class has a constructor, a destructor, and two methods: `append` and `dump`.
- The `Collector` class has two constructors: one that takes no arguments and one that takes an integer argument. The constructor that takes an integer argument allocates memory for the list of integers.
- The `Collector` class has a destructor that frees the memory allocated for the list of integers.
- The `Collector` class has a method called `append` that appends an integer to the list of integers. If the list is full, the method returns `false`. Otherwise, the method returns `true`.
- The `Collector` class has a method called `dump` that prints the list of integers.
- In the `main` function, we create an instance of the `Collector` class. We then append the integers `0` through `9` to the list of integers. Finally, we call the `dump` method to print the list of integers.
- When the `main` function returns, the instance of the `Collector` class goes out of scope. This means that the destructor is called and the memory allocated for the list of integers is freed.

**Output:**

```bash
0 1 2 3 4 5 6 7 8 9
Destructor called
```