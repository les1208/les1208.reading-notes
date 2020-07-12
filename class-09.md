## LINQ & Delegates

#### Language Integrated Query (LINQ
- Language-Integrated Query (LINQ) is the name for a set of technologies based on the integration of query capabilities directly into the C# language. Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support. Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on. With LINQ, a query is a first-class language construct, just like classes, methods, events. You write queries against strongly typed collections of objects by using language keywords and familiar operators. The LINQ family of technologies provides a consistent query experience for objects (LINQ to Objects), relational databases (LINQ to SQL), and XML (LINQ to XML).

- For a developer who writes queries, the most visible "language-integrated" part of LINQ is the query expression. Query expressions are written in a declarative query syntax. By using query syntax, you can perform filtering, ordering, and grouping operations on data sources with a minimum of code. You use the same basic query expression patterns to query and transform data in SQL databases, ADO.NET Datasets, XML documents and streams, and .NET collections.

- You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports IEnumerable or the generic IEnumerable<T> interface. LINQ support is also provided by third parties for many Web services and other database implementations.

#### Query expression overview
- Query expressions can be used to query and to transform data from any LINQ-enabled data source. For example, a single query can retrieve data from a SQL database, and produce an XML stream as output.
- Query expressions are easy to master because they use many familiar C# language constructs.
- The variables in a query expression are all strongly typed, although in many cases you do not have to provide the type explicitly because the compiler can infer it. For more information, see Type relationships in LINQ query operations.
- A query is not executed until you iterate over the query variable, for example, in a foreach statement. For more information, see Introduction to LINQ queries.
- At compile time, query expressions are converted to Standard Query Operator method calls according to the rules set forth in the C# specification. Any query that can be expressed by using query syntax can also be expressed by using method syntax. However, in most cases query syntax is more readable and concise. For more information, see C# language specification and Standard query operators overview.
- As a rule when you write LINQ queries, we recommend that you use query syntax whenever possible and method syntax whenever necessary. There is no semantic or performance difference between the two different forms. Query expressions are often more readable than equivalent expressions written in method syntax.
- Some query operations, such as Count or Max, have no equivalent query expression clause and must therefore be expressed as a method call. Method syntax can be combined with query syntax in various ways. For more information, see Query syntax and method syntax in LINQ.
- Query expressions can be compiled to expression trees or to delegates, depending on the type that the query is applied to. IEnumerable<T> queries are compiled to delegates. IQueryable and IQueryable<T> queries are compiled to expression trees. For more information, see Expression trees.

#### Introduction to LINQ Queries (C#)
- A query is an expression that retrieves data from a data source. Queries are usually expressed in a specialized query language. Different languages have been developed over time for the various types of data sources, for example SQL for relational databases and XQuery for XML. Therefore, developers have had to learn a new query language for each type of data source or data format that they must support. LINQ simplifies this situation by offering a consistent model for working with data across various kinds of data sources and formats. In a LINQ query, you are always working with objects. You use the same basic coding patterns to query and transform data in XML documents, SQL databases, ADO.NET Datasets, .NET collections, and any other format for which a LINQ provider is available.

##### Three Parts of a Query Operation
- All LINQ query operations consist of three distinct actions:

1. Obtain the data source.

2. Create the query.

3. Execute the query.

##### The Data Source
- In the previous example, because the data source is an array, it implicitly supports the generic IEnumerable<T> interface. This fact means it can be queried with LINQ. A query is executed in a foreach statement, and foreach requires IEnumerable or IEnumerable<T>. Types that support IEnumerable<T> or a derived interface such as the generic IQueryable<T> are called queryable types.

- A queryable type requires no modification or special treatment to serve as a LINQ data source. If the source data is not already in memory as a queryable type, the LINQ provider must represent it as such

##### The Query
- The query specifies what information to retrieve from the data source or sources. Optionally, a query also specifies how that information should be sorted, grouped, and shaped before it is returned. A query is stored in a query variable and initialized with a query expression. To make it easier to write queries, C# has introduced new query syntax.

- The query in the previous example returns all the even numbers from the integer array. The query expression contains three clauses: from, where and select. (If you are familiar with SQL, you will have noticed that the ordering of the clauses is reversed from the order in SQL.) The from clause specifies the data source, the where clause applies the filter, and the select clause specifies the type of the returned elements. These and the other query clauses are discussed in detail in the Language Integrated Query (LINQ) section. For now, the important point is that in LINQ, the query variable itself takes no action and returns no data. It just stores the information that is required to produce the results when the query is executed at some later point.

##### Query Execution
Deferred Execution
As stated previously, the query variable itself only stores the query commands. The actual execution of the query is deferred until you iterate over the query variable in a foreach statement

- The foreach statement is also where the query results are retrieved. For example, in the previous query, the iteration variable num holds each value (one at a time) in the returned sequence.

- Because the query variable itself never holds the query results, you can execute it as often as you like. For example, you may have a database that is being updated continually by a separate application. In your application, you could create one query that retrieves the latest data, and you could execute it repeatedly at some interval to retrieve different results every time.

#### Basic LINQ Query Operations (C#)

##### Obtaining a Data Source
- In a LINQ query, the first step is to specify the data source. In C# as in most programming languages a variable must be declared before it can be used. In a LINQ query, the from clause comes first in order to introduce the data source (customers) and the range variable (cust).

- The range variable is like the iteration variable in a foreach loop except that no actual iteration occurs in a query expression. When the query is executed, the range variable will serve as a reference to each successive element in customers. Because the compiler can infer the type of cust, you do not have to specify it explicitly. Additional range variables can be introduced by a let clause.

##### Filtering
- Probably the most common query operation is to apply a filter in the form of a Boolean expression. The filter causes the query to return only those elements for which the expression is true. The result is produced by using the where clause. The filter in effect specifies which elements to exclude from the source sequence. In the following example, only those customers who have an address in London are returned.

##### Ordering
- Often it is convenient to sort the returned data. The orderby clause will cause the elements in the returned sequence to be sorted according to the default comparer for the type being sorted. For example, the following query can be extended to sort the results based on the Name property. Because Name is a string, the default comparer performs an alphabetical sort from A to Z.

##### Joining
- Join operations create associations between sequences that are not explicitly modeled in the data sources. For example you can perform a join to find all the customers and distributors who have the same location. In LINQ the join clause always works against object collections instead of database tables directly.

##### Selecting (Projections)
- The select clause produces the results of the query and specifies the "shape" or type of each returned element. For example, you can specify whether your results will consist of complete Customer objects, just one member, a subset of members, or some completely different result type based on a computation or new object creation. When the select clause produces something other than a copy of the source element, the operation is called a projection. The use of projections to transform data is a powerful capability of LINQ query expressions. For more information, see Data Transformations with LINQ (C#) and select clause.

##### Walkthrough: Writing Queries in C# (LINQ)
- Create a C# Project

To create a project in Visual Studio
Start Visual Studio.

On the menu bar, choose File, New, Project.

The New Project dialog box opens.

Expand Installed, expand Templates, expand Visual C#, and then choose Console Application.

In the Name text box, enter a different name or accept the default name, and then choose the OK button.

The new project appears in Solution Explorer.

Notice that your project has a reference to System.Core.dll and a using directive for the System.Linq namespace.

- Create an in-Memory Data Source
The data source for the queries is a simple list of Student objects. Each Student record has a first name, last name, and an array of integers that represents their test scores in the class. Copy this code into your project. Note the following characteristics:

The Student class consists of auto-implemented properties.

Each student in the list is initialized with an object initializer.

The list itself is initialized with a collection initializer.

This whole data structure will be initialized and instantiated without explicit calls to any constructor or explicit member access. For more information about these new features, see Auto-Implemented Properties and Object and Collection Initializers.

#### Create the Query
- To create a simple query
- In the application's Main method, create a simple query that, when it is executed, will produce a list of all students whose score on the first test was greater than 90. Note that because the whole Student object is selected, the type of the query is IEnumerable<Student>. Although the code could also use implicit typing by using the var keyword, explicit typing is used to clearly illustrate results. (For more information about var, see Implicitly Typed Local Variables.)

#### Execute the Query
- To execute the query
- Now write the foreach loop that will cause the query to execute. Note the following about the code:

- Each element in the returned sequence is accessed through the iteration variable in the foreach loop.

- The type of this variable is Student, and the type of the query variable is compatible, IEnumerable<Student>.

- After you have added this code, build and run the application to see the results in the Console window.