## Classes & Objects, & Memory Management 
#### Referance Types
- When an array is created, it needs a certain amount of memory. If we had 7 letters that we needed to store in an array, we would need 7 bytes of memory to represent that array. But, we’d need all of that memory in one contiguous block. That is to say, our computer would need to locate 7 bytes of memory that was free, one byte next to the another, all together, in one place.
- On the other hand, when a linked list is born, it doesn’t need 7 bytes of memory all in one place. One byte could live somewhere, while the next byte could be stored in another place in memory altogether! Linked lists don’t need to take up a single block of memory; instead, the memory that they use can be scattered throughout.
- When the object is created, enough memory is allocated on the managed heap for that specific object, and the variable holds only a reference to the location of said object. Types on the managed heap require overhead both when they are allocated and when they are reclaimed by the automatic memory management functionality of the CLR, which is known as garbage collection. However, garbage collection is also highly optimized and in most scenarios, it does not create a performance issue
#### Declaring Classes
- The class keyword is preceded by the access level. Because public is used in this case, anyone can create instances of this class. The name of the class follows the class keyword. The name of the class must be a valid C# identifier name. The remainder of the definition is the class body, where the behavior and data are defined. Fields, properties, methods, and events on a class are collectively referred to as class members.

#### Creating objects
- Although they are sometimes used interchangeably, a class and an object are different things. A class defines a type of object, but it is not an object itself. An object is a concrete entity based on a class, and is sometimes referred to as an instance of a class.

- Objects can be created by using the new keyword followed by the name of the class that the object will be based on.
#### Class inheritance
- Classes fully support inheritance, a fundamental characteristic of object-oriented programming. 
When you create a class, you can inherit from any other interface or class that is not defined as sealed, and other classes can inherit from your class and override class virtual methods.
#### Constructors
- Whenever a class or struct is created, its constructor is called. A class or struct may have multiple constructors that take different arguments. Constructors enable the programmer to set default values, limit instantiation, and write code that is flexible and easy to read. For more information and examples, see Using Constructors and Instance Constructors.

#### Parameterless constructors
- If you don't provide a constructor for your class, C# creates one by default that instantiates the object and sets member variables to the default values as listed in the Default values of C# types article. If you don't provide a constructor for your struct, C# relies on an implicit parameterless constructor to automatically initialize each field to its default value. For more information and examples, see Instance constructors.

#### Constructor syntax
- A constructor is a method whose name is the same as the name of its type. Its method signature includes only the method name and its parameter list; it does not include a return type. The following example shows the constructor for a class named Person.

C#

Copy
public class Person
{
   private string last;
   private string first;

   public Person(string lastName, string firstName)
   {
      last = lastName;
      first = firstName;
   }

   // Remaining implementation of Person class.
}
If a constructor can be implemented as a single statement, you can use an expression body definition. The following example defines a Location class whose constructor has a single string parameter named name. The expression body definition assigns the argument to the locationName field.

C#

Copy
public class Location
{
   private string locationName;

   public Location(string name) => Name = name;

   public string Name
   {
      get => locationName;
      set => locationName = value;
   }
}
#### Static constructors
- The previous examples have all shown instance constructors, which create a new object. A class or struct can also have a static constructor, which initializes static members of the type. Static constructors are parameterless. If you don't provide a static constructor to initialize static fields, the C# compiler initializes static fields to their default value as listed in the Default values of C# types article.

#### Properties 
- A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field. Properties can be used as if they are public data members, but they are actually special methods called accessors. This enables data to be accessed easily and still helps promote the safety and flexibility of methods.

#### Properties overview
- Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.

- A get property accessor is used to return the property value, and a set property accessor is used to assign a new value. These accessors can have different access levels. For more information, see Restricting Accessor Accessibility.

- The value keyword is used to define the value being assigned by the set accessor.

- Properties can be read-write (they have both a get and a set accessor), read-only (they have a get accessor but no set accessor), or write-only (they have a set accessor, but no get accessor). Write-only properties are rare and are most commonly used to restrict access to sensitive data.

- Simple properties that require no custom accessor code can be implemented either as expression body definitions or as auto-implemented properties.

#### Auto-implemented properties
- In some cases, property get and set accessors just assign a value to or retrieve a value from a backing field without including any additional logic. By using auto-implemented properties, you can simplify your code while having the C# compiler transparently provide the backing field for you.

- If a property has both a get and a set accessor, both must be auto-implemented. You define an auto-implemented property by using the get and set keywords without providing any implementation. The following example repeats the previous one, except that Name and Price are auto-implemented properties. Note that the example also removes the parameterized constructor, so that SaleItem objects are now initialized with a call to the parameterless constructor and an object initializer.

#### Fundamentals of garbage collection

- In the common language runtime (CLR), the garbage collector (GC) serves as an automatic memory manager. The garbage collector manages the allocation and release of memory for an application. For developers working with managed code, this means that you don't have to write code to perform memory management tasks. Automatic memory management can eliminate common problems, such as forgetting to free an object and causing a memory leak or attempting to access memory for an object that's already been freed.

This article describes the core concepts of garbage collection.

Benefits
The garbage collector provides the following benefits:

Frees developers from having to manually release memory.

Allocates objects on the managed heap efficiently.

Reclaims objects that are no longer being used, clears their memory, and keeps the memory available for future allocations. Managed objects automatically get clean content to start with, so their constructors don't have to initialize every data field.

Provides memory safety by making sure that an object cannot use the content of another object.

Fundamentals of memory
The following list summarizes important CLR memory concepts.

Each process has its own, separate virtual address space. All processes on the same computer share the same physical memory and the page file, if there is one.

By default, on 32-bit computers, each process has a 2-GB user-mode virtual address space.

As an application developer, you work only with virtual address space and never manipulate physical memory directly. The garbage collector allocates and frees virtual memory for you on the managed heap.

If you're writing native code, you use Windows functions to work with the virtual address space. These functions allocate and free virtual memory for you on native heaps.

Virtual memory can be in three states:

TABLE 1
State	Description
Free	The block of memory has no references to it and is available for allocation.
Reserved	The block of memory is available for your use and cannot be used for any other allocation request. However, you cannot store data to this memory block until it is committed.
Committed	The block of memory is assigned to physical storage.
Virtual address space can get fragmented. This means that there are free blocks, also known as holes, in the address space. When a virtual memory allocation is requested, the virtual memory manager has to find a single free block that is large enough to satisfy that allocation request. Even if you have 2 GB of free space, an allocation that requires 2 GB will be unsuccessful unless all of that free space is in a single address block.

You can run out of memory if there isn't enough virtual address space to reserve or physical space to commit.

The page file is used even if physical memory pressure (that is, demand for physical memory) is low. The first time that physical memory pressure is high, the operating system must make room in physical memory to store data, and it backs up some of the data that is in physical memory to the page file. That data is not paged until it's needed, so it's possible to encounter paging in situations where the physical memory pressure is low.
