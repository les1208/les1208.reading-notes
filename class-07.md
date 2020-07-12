## Interfaces
https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/inheritance

- Inheritance, together with encapsulation and polymorphism, is one of the three primary characteristics of object-oriented programming. Inheritance enables you to create new classes that reuse, extend, and modify the behavior defined in other classes.
- The class whose members are inherited is called the base class, and the class that inherits those members is called the derived class. A derived class can have only one direct base class. However, inheritance is transitive. If ClassC is derived from ClassB, and ClassB is derived from ClassA, ClassC inherits the members declared in ClassB and ClassA.
- Interface declarations may define a default implementation for its members. These implementations are inherited by derived interfaces, and by classes that implement those interfaces. For more information on default interface methods, see the article on interfaces in the language reference section.
- When you define a class to derive from another class, the derived class implicitly gains all the members of the base class, except for its constructors and finalizers. The derived class reuses the code in the base class without having to reimplement it. You can add more members in the derived class. The derived class extends the functionality of the base class.
#### Abstract and virtual methods
- When a base class declares a method as virtual, a derived class can override the method with its own implementation. If a base class declares a member as abstract, that method must be overridden in any non-abstract class that directly inherits from that class. If a derived class is itself abstract, it inherits abstract members without implementing them. Abstract and virtual members are the basis for polymorphism, which is the second primary characteristic of object-oriented programming. For more information, see Polymorphism.
#### Abstract base classes
- You can declare a class as abstract if you want to prevent direct instantiation by using the new operator. An abstract class can be used only if a new class is derived from it. An abstract class can contain one or more method signatures that themselves are declared as abstract. These signatures specify the parameters and return value but have no implementation (method body). An abstract class doesn't have to contain abstract members; however, if a class does contain an abstract member, the class itself must be declared as abstract. Derived classes that aren't abstract themselves must provide the implementation for any abstract methods from an abstract base class.
#### Interfaces
- An interface is a reference type that defines a set of members. All classes and structs that implement that interface must implement that set of members. An interface may define a default implementation for any or all of these members. A class can implement multiple interfaces even though it can derive from only a single direct base class.

- Interfaces are used to define specific capabilities for classes that don't necessarily have an "is a" relationship.

- A class can prevent other classes from inheriting from it, or from any of its members, by declaring itself or the member as sealed. 

- A derived class can hide base class members by declaring members with the same name and signature. The new modifier can be used to explicitly indicate that the member isn't intended to be an override of the base member. The use of new isn't required, but a compiler warning will be generated if new isn't used.


https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members
- The abstract keyword enables you to create classes and class members that are incomplete and must be implemented in a derived class.

- The sealed keyword enables you to prevent the inheritance of a class or certain class members that were previously marked virtual.

- An abstract class cannot be instantiated. The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share. For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.

- Abstract classes may also define abstract methods. This is accomplished by adding the keyword abstract before the return type of the method
- Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block. Derived classes of the abstract class must implement all abstract methods. When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.
- If a virtual method is declared abstract, it is still virtual to any class inheriting from the abstract class. A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, DoWork on class F cannot call DoWork on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.
- A sealed class cannot be used as a base class. For this reason, it cannot also be an abstract class. Sealed classes prevent derivation. Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.
- A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed. This negates the virtual aspect of the member for any further derived class. This is accomplished by putting the sealed keyword before the override keyword in the class member declaration.

https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/polymorphism
#### Polymorphism
- Polymorphism is often referred to as the third pillar of object-oriented programming, after encapsulation and inheritance. Polymorphism is a Greek word that means "many-shaped" and it has two distinct aspects:

- At run time, objects of a derived class may be treated as objects of a base class in places such as method parameters and collections or arrays. When this polymorphism occurs, the object's declared type is no longer identical to its run-time type.
- Base classes may define and implement virtual methods, and derived classes can override them, which means they provide their own definition and implementation. At run-time, when client code calls the method, the CLR looks up the run-time type of the object, and invokes that override of the virtual method. In your source code you can call a method on a base class, and cause a derived class's version of the method to be executed.
- Virtual methods enable you to work with groups of related objects in a uniform way. For example, suppose you have a drawing application that enables a user to create various kinds of shapes on a drawing surface. You do not know at compile time which specific types of shapes the user will create. However, the application has to keep track of all the various types of shapes that are created, and it has to update them in response to user mouse actions. You can use polymorphism to solve this problem in two basic steps:

- Create a class hierarchy in which each specific shape class derives from a common base class.
- Use a virtual method to invoke the appropriate method on any derived class through a single call to the base class method.
#### Polymorphism overview
-Virtual members
When a derived class inherits from a base class, it gains all the methods, fields, properties, and events of the base class. The designer of the derived class can different choices for the behavior of virtual methods:

-The derived class may override virtual members in the base class, defining new behavior.
- The derived class inherit the closest base class method without overriding it, preserving the existing behavior but enabling further derived classes to override the method.
- The derived class may define new non-virtual implementation of those members that hide the base class implementations.
- A derived class can override a base class member only if the base class member is declared as virtual or abstract. The derived member must use the override keyword to explicitly indicate that the method is intended to participate in virtual invocation. 
- Fields cannot be virtual; only methods, properties, events, and indexers can be virtual. When a derived class overrides a virtual member, that member is called even when an instance of that class is being accessed as an instance of the base class. 
#### Object-Oriented programming (C#)
C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.

- Abstraction means hiding the unnecessary details from type consumers.
- Encapsulation means that a group of related properties, methods, and other members are treated as a single unit or object.
- Inheritance describes the ability to create new classes based on an existing class.
- Polymorphism means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.

#### Classes and objects
- The terms class and object describe the type of objects, and the instances of classes, respectively. So, the act of creating an object is called instantiation. Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.
- C# also provides types called structures that are useful when you don't need support for inheritance or polymorphism

##### Class members
- Each class can have different class members that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.

##### Properties and fields
- Fields and properties represent information that an object contains. Fields are like variables because they can be read or set directly, subject to applicable access modifiers.

- Properties have get and set accessors, which provide more control on how values are set or returned.

- C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.

##### Methods
- A method is an action that an object can perform.
- A class can have several implementations, or overloads, of the same method that differ in the number of parameters or parameter types.
- In most cases you declare a method within a class definition. However, C# also supports extension methods that allow you to add methods to an existing class outside the actual definition of the class.
##### Constructors
- Constructors are class methods that are executed automatically when an object of a given type is created. Constructors usually initialize the data members of the new object. A constructor can run only once when a class is created. Furthermore, the code in the constructor always runs before any other code in a class. However, you can create multiple constructor overloads in the same way as for any other method.
##### Finalizers
- A finalizer is used to destruct instances of classes. In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application. However, you may still need finalizers to clean up any unmanaged resources that your application creates. There can be only one finalizer for a class.

##### Events
- Events enable a class or object to notify other classes or objects when something of interest occurs. The class that sends (or raises) the event is called the publisher and the classes that receive (or handle) the event are called subscribers. For more information about events, how they are raised and handled, see Events.

- To declare an event in a class, use the event keyword.
- To raise an event, invoke the event delegate.
- To subscribe to an event, use the += operator; to unsubscribe from an event, use the -= operator.

##### Nested classes
- A class defined within another class is called nested. By default, the nested class is private.

- To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:
** Container.Nested nestedInstance = new Container.Nested() **

#### Access modifiers and access levels
- All classes and class members can specify what access level they provide to other classes by using access modifiers.

ACCESS MODIFIERS AND ACCESS LEVELS
C# Modifier	Definition
* public	The type or member can be accessed by any other code in the same assembly or another assembly that references it.
* private	The type or member can only be accessed by code in the same class.
* protected	The type or member can only be accessed by code in the same class or in a derived class.
* internal	The type or member can be accessed by any code in the same assembly, but not from another assembly.
* protected internal	The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.
* private protected	The type or member can be accessed by code in the same class or in a derived class within the base class assembly.
#### Instantiating classes
- To create an object, you need to instantiate a class, or create a class instance.

- SampleClass sampleObject = new SampleClass();
- After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.
##### Static Classes and Members
- A static member of the class is a property, procedure, or field that is shared by all instances of a class.
- To define a static member:

static class SampleClass
{
    public static string SampleString = "Sample String";
}
To access the static member, use the name of the class without creating an object of this class:

Console.WriteLine(SampleClass.SampleString);
- Static classes in C# have static members only and cannot be instantiated. Static members also cannot access non-static properties, fields or methods

##### Anonymous types
- Anonymous types enable you to create objects without writing a class definition for the data type. Instead, the compiler generates a class for you. The class has no usable name and contains the properties you specify in declaring the object.

##### Inheritance
- Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class. The class whose members are inherited is called the base class, and the class that inherits those members is called the derived class. However, all classes in C# implicitly inherit from the Object class that supports .NET class hierarchy and provides low-level services to all classes.