# OOP Study Guide: 

### UML Multiplicity
UML multiplicity is a property of a relationship between two elements in a UML diagram. It defines the number of instances of one element that can be related to one instance of the other element. It is important to understand the type of relationship that exists between the two elements (associations, generalization, composition, etc.) in order to correctly determine the multiplicity.

### Generalization (Inheritance) IS A
Generalization (inheritance) is when a descendant inherits the features of its ancestor. This can be used to reduce code duplication and to create more organized and reusable code. It is important to understand the differences between direct inheritance from a Base class, inheritance from Handler used by a Base class, and C++ Templates. 

Used to solve Design problems, If you do not have a design problem do not use Generalization

### Composition and Aggregation
Both composition and aggregation are specific cases of association, where an object of one class "owns" an object of another class. The difference between them lies in the dependency of the child object on the parent object.

- **Aggregation: In aggregation, the child object can exist independently of the parent object. For example, a Class (parent) and a Student (child). If the Class is deleted, the Students still exist. To represent aggregation in a UML diagram, draw a line from the parent class to the child class with a diamond shape near the parent class**

- **Composition: In composition, the child object cannot exist independently of the parent object. For example, a House (parent) and a Room (child). Rooms do not exist separately from a House. To represent composition in a UML diagram, use a directional line connecting the two classes, with a filled diamond shape adjacent to the container class and the directional arrow to the contained class**

### When to use Composition over Aggregation
The choice between composition and aggregation depends on the desired relationship between the parent and child objects. If the child object should be destroyed when the parent object is destroyed, use composition. If the child object should continue to exist independently of the parent object, use aggregation

### Extension Points: Implementations
#### A) Direct Inheritance from a Base Class
Direct inheritance involves creating a derived class that inherits properties and behavior from a base class. The derived class can reuse, extend, and modify the behavior defined in the base class. This approach minimizes code duplication and increases reusability (learn.microsoft.com).

Example:
 ```
class Animal {
public:
    void makeSound() { /*...*/ }
};

class Dog : public Animal {
    // Inherits makeSound() from Animal
};
 ```
Pros:
- Reduces code duplication
- Increases reusability
- Simplifies code maintenance

Cons:
- Inflexible when it comes to multiple inheritance (C++ supports multiple inheritance, but it can lead to ambiguity and complexity)

#### B) Inheritance from Handler used by a Base Class
This approach involves creating a base class that uses a handler (or a delegate) to implement certain behaviors. The derived class can inherit from the handler, allowing for greater flexibility and customization.

Example:
 ```
class AnimalSoundHandler {
public:
    virtual void makeSound() { /*...*/ }
};

class Animal {
public:
    void setSoundHandler(AnimalSoundHandler* handler) { soundHandler = handler; }
    void makeSound() { soundHandler->makeSound(); }

private:
    AnimalSoundHandler* soundHandler;
};

class DogSoundHandler : public AnimalSoundHandler {
public:
    void makeSound() override { /*...*/ } // Overrides the base class implementation
};

class Dog : public Animal {
    // Inherits from Animal and uses DogSoundHandler for makeSound()
};
 ```
Pros:
- Greater flexibility in managing behaviors.
- Allows for easier customization of derived classes

Cons:
- More complex implementation.
- May lead to increased memory usage due to additional objects (handlers)

#### C) C++ Templates
Templates allow for generic programming, enabling the creation of classes and functions with placeholder types. This approach can provide greater flexibility and reusability.

Example:
 ```
template <typename T>
class Animal {
public:
    void makeSound() { soundMaker.makeSound(); }

private:
    T soundMaker;
};

class DogSoundMaker {
public:
    void makeSound() { /*...*/ }
};

using Dog = Animal<DogSoundMaker>; // Dog is an Animal with DogSoundMaker as its sound maker
 ```
Pros:
- Highly flexible and reusable
- Allows for compile-time polymorphism

Cons:
- May lead to increased code size due to template instantiations
- Can be more complex to implement and understand

Direct inheritance is simpler to implement and understand, but it may not provide the flexibility needed for more complex scenarios. Inheritance from a handler can offer greater customization, but it may lead to increased complexity and memory usage. C++ templates provide a high degree of flexibility and reusability, but they can also lead to increased code size and complexity.


### RAII
RAII stands for “Resource Acquisition Is Initialization”. It is a programming technique used to ensure that resources are allocated and released properly in a program. It is important because it helps to avoid memory leaks and other errors that can arise from improper resource management. RAII can be implemented by using smart pointers, smart references, and RAII classes. 

Resource Acquisition Is Initialization (RAII) is a programming idiom used in C++ and other languages to manage resources such as memory, file handles, and network connections. It involves tying the lifetime of a resource to the lifetime of an object, ensuring that the resource is acquired during object construction and released during object destruction.

#### Why RAII is important:

- It eliminates resource leaks by automatically releasing resources when the object goes out of scope.
- It simplifies code by reducing the need for explicit resource management, such as manual memory deallocation or closing file handles.
- It improves exception safety by ensuring that resources are released even if an exception occurs during the object's lifetime.

#### How to implement RAII:

1. **Encapsulate the resource in a class, with the resource acquisition occurring in the class constructor and resource release occurring in the class destructor.**

Example:
 ```
class FileHandle {
public:
    FileHandle(const std::string& filename) {
        file_ = fopen(filename.c_str(), "r");
        if (!file_) {
            throw std::runtime_error("Unable to open file");
        }
    }

    ~FileHandle() {
        fclose(file_);
    }

private:
    FILE* file_;
};
 ```
In this example, the FileHandle class wraps a file handle, acquiring the resource in the constructor and releasing it in the destructor.

2. **Use smart pointers, such as std::unique_ptr or std::shared_ptr, to manage dynamically allocated objects. These smart pointers automatically take care of memory management and ensure that the allocated objects are properly deleted when they are no longer needed.**

Example:
 ```
std::unique_ptr<MyClass> ptr(new MyClass());
 ```
In this example, the std::unique_ptr manages the lifetime of the MyClass object, automatically deleting it when the smart pointer goes out of scope.

3. **If possible, prefer to use Standard Library containers and algorithms, as they are designed with RAII in mind and often provide built-in resource management.**

Example:
 ```
std::vector<int> myVector;
 ```
In this example, the std::vector container manages the memory allocation and deallocation for its elements, ensuring that no memory leaks occur.

By following these RAII principles and practices, you can write more robust, maintainable, and efficient code that is less prone to resource leaks and other common programming errors.

### Coupling
Coupling is the degree of interdependence between two modules or components of a system. It is important to reduce coupling in order to make the system more maintainable and easier to understand. Some ways to reduce coupling include modularization, abstraction, and decoupling.

Degree of interdependence between software modules; a measure of how closely connected two routines or modules are; the strength of the relationships between modules.

### Dependency Injection
Dependency Injection is a design pattern in which an external source is used to provide objects to a class. The external source can be a configuration file, a database, or another service. Dependency Injection helps to make code more testable and maintainable by allowing it to be decoupled from the external source.

Dependency injection is a programming technique that involves injecting dependencies into a class or function. There are several approaches to implementing dependency injection, including constructor injection, setter injection, and interface injection. Dependency injection has several benefits, including decoupling, testability, and reusability. By using dependency injection, programmers can create code that is more flexible, efficient, and easier to maintain.

Define a family of algorithms, encapsulate each one, and make them interchangeable. Strategy lets the algorithm vary independently from clients that use it.

Advantages:
- Decouples code
- Allows for rich testing
- Frameworks for creating mock objects
- Each class has a more direct purpose

Disadvantages:
- Creates more classes
- Obliged to do better testing
- Introduces a controlled increase in complexity

### Encapsulation 
*The bundling of data with the methods that operate on that data* Encapsulation is the process of wrapping data and functions in one unit. It helps to reduce complexity and promote the reusability of code. 

### Information Hiding
*Hide the internal representation, or state, of an object from the outside* Information Hiding is the process of hiding the implementation details of a class from the outside world. It helps to make code more maintainable and easier to understand.

### Dispatch 
Dispatch is the process of deciding which function to call in a program. Static dispatch is when the decision is made at compile-time, while dynamic dispatch is when the decision is made at run-time. It is important to understand the differences between static and dynamic dispatch when deciding which approach to use in a program.

### Extra 
vtable is a data structure used in object-oriented programming languages to store pointers to virtual functions. It is important to understand how vtables work in order to correctly implement and use virtual functions in a program.