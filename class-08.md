## Collections & Enums

#### Collections
- For many applications, you want to create and manage groups of related objects. There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.

- Arrays are most useful for creating and working with a fixed number of strongly typed objects. For information about arrays, see Arrays.

- Collections provide a more flexible way to work with groups of objects. Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change. For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.

- A collection is a class, so you must declare an instance of the class before you can add elements to that collection.

- If your collection contains elements of only one data type, you can use one of the classes in the System.Collections.Generic namespace. A generic collection enforces type safety so that no other data type can be added to it. When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.

- You can use a for statement instead of a foreach statement to iterate through a collection. You accomplish this by accessing the collection elements by the index position. The index of the elements starts at 0 and ends at the element count minus 1.

#### Kinds of Collections
- Many common collections are provided by .NET. Each type of collection is designed for a specific purpose.

* Some of the common collection classes are described in this section:

* System.Collections.Generic classes

* System.Collections.Concurrent classes

* System.Collections classes


- System.Collections.Generic Classes
- You can create a generic collection by using one of the classes in the System.Collections.Generic namespace. A generic collection is useful when every item in the collection has the same data type. A generic collection enforces strong typing by allowing only the desired data type to be added.

The following table lists some of the frequently used classes of the System.Collections.Generic namespace:

SYSTEM.COLLECTIONS.GENERIC CLASSES
Class	Description
Dictionary<TKey,TValue>	Represents a collection of key/value pairs that are organized based on the key.
List<T>	Represents a list of objects that can be accessed by index. Provides methods to search, sort, and modify lists.
Queue<T>	Represents a first in, first out (FIFO) collection of objects.
SortedList<TKey,TValue>	Represents a collection of key/value pairs that are sorted by key based on the associated IComparer<T> implementation.
Stack<T>	Represents a last in, first out (LIFO) collection of objects.

#### Iterators
-  An iterator is used to perform a custom iteration over a collection. An iterator can be a method or a get accessor. An iterator uses a yield return statement to return each element of the collection one at a time.

- You call an iterator by using a foreach statement. Each iteration of the foreach loop calls the iterator. When a yield return statement is reached in the iterator, an expression is returned, and the current location in code is retained. Execution is restarted from that location the next time that the iterator is called.

#### Enumeration types (C# reference)
- An enumeration type (or enum type) is a value type defined by a set of named constants of the underlying integral numeric type. To define an enumeration type, use the enum keyword and specify the names of enum members:
- By default, the associated constant values of enum members are of type int; they start with zero and increase by one following the definition text order. You can explicitly specify any other integral numeric type as an underlying type of an enumeration type. You can also explicitly specify the associated constant values
- You cannot define a method inside the definition of an enumeration type. To add functionality to an enumeration type, create an extension method.

- The default value of an enumeration type E is the value produced by expression (E)0, even if zero doesn't have the corresponding enum member.

- You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices. To represent a combination of choices, define an enumeration type as bit flags.

