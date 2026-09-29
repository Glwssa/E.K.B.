# Modern C# & .NET — Consolidated Study Notes

> Based on the latest canonical **Architectural Talk** roadmap for **Category 1 — Modern C# & .NET**.
>
> This document contains only material that was actually taught or meaningfully discussed in this chat. Earlier explanations are replaced by their latest corrected versions. Project-, employer-, and company-specific examples are removed or replaced with neutral examples.
>
> The main body is organized by **P0 topic**. Material that belongs to **P1 Runtime & Diagnostics** is kept in a separate appendix so it is not misclassified.

---

# What This Document Covers

This document covers the material taught in this chat for **Category 1 — Modern C# & .NET** of the latest canonical learning roadmap.

## P0 — Professional C# Fundamentals

Covered in this document:

- Value types vs reference types
- Copying and parameter passing
- Boxing and unboxing
- Classes, structs, records, and record structs
- Equality and hashing
- Immutability, `readonly`, `init`, and `required`
- Nullable reference types and null-state analysis
- Shallow vs deep copying
- Interfaces and abstraction
- Abstract classes, inheritance, composition, and polymorphism
- Access modifiers
- Generics and generic constraints
- Variance
- Collection abstractions and concrete collections
- LINQ fundamentals
- Deferred execution and materialization
- `IEnumerable<T>` vs `IQueryable<T>`
- `First`, `Single`, and `Any`
- Grouping, lookup, and duplicate handling
- LINQ joins
- Delegates, `Action`, and `Func`
- Lambdas and closures
- Events
- Expression trees
- Pattern matching
- Exceptions and exception flow
- `IDisposable`, `IAsyncDisposable`, and ownership
- `Span<T>` / `ReadOnlySpan<T>`
- `Memory<T>` / `ReadOnlyMemory<T>`
- `stackalloc`
- `ArrayPool<T>`
- Attributes
- Reflection fundamentals
- Source-generation fundamentals
- Modern C# / C# 14 backend-relevant features

## P0 — Async & Concurrency

Covered in this document:

- `Task` / `Task<T>`
- `async` / `await`
- I/O-bound vs CPU-bound work
- Sequential vs concurrent async work
- Cancellation and `CancellationToken`
- Avoiding sync-over-async
- `async void`
- `ValueTask<T>`
- `Task.WhenAll`
- `Task.WhenAny`
- Timeouts
- Process vs thread vs task
- Race conditions
- `Interlocked`
- `lock`
- `SemaphoreSlim`
- Concurrent collections
- Deadlocks
- `Channel<T>`
- ThreadPool starvation
- Concurrency vs parallelism
- Bounded concurrency
- `Parallel.ForEachAsync`
- `IAsyncEnumerable<T>`

## P1 Material Also Discussed

The appendix includes the P1 runtime material that was taught in the chat:

- CLR, IL, and JIT
- stack frames and object lifetime
- managed heap and GC reachability
- GC generations
- Large Object Heap
- allocation pressure
- managed memory retention

---

# Navigation

- [P0 — Professional C# Fundamentals]
  - [1. Value types vs reference types](#1-value-types-vs-reference-types)
  - [2. Copying and parameter passing](#2-copying-and-parameter-passing)
  - [3. Boxing and unboxing](#3-boxing-and-unboxing)
  - [4. `class`, `struct`, `record`, and `record struct`](#4-class-struct-record-and-record-struct)
  - [5. Equality and hashing](#5-equality-and-hashing)
  - [6. Immutability, `readonly`, `init`, and `required`](#6-immutability-readonly-init-and-required)
  - [7. Nullable reference types and null-state analysis](#7-nullable-reference-types-and-null-state-analysis)
  - [8. Shallow vs deep copying](#8-shallow-vs-deep-copying)
  - [9. Interfaces and abstraction](#9-interfaces-and-abstraction)
  - [10. Abstract classes, inheritance, composition, and polymorphism](#10-abstract-classes-inheritance-composition-and-polymorphism)
  - [11. Access modifiers](#11-access-modifiers)
  - [12. Generics](#12-generics)
  - [13. Variance](#13-variance)
  - [14. Collection abstractions](#14-collection-abstractions)
  - [15. Concrete collections](#15-concrete-collections)
  - [16. LINQ fundamentals](#16-linq-fundamentals)
  - [17. Deferred execution and materialization](#17-deferred-execution-and-materialization)
  - [18. `IEnumerable<T>` vs `IQueryable<T>`](#18-ienumerablet-vs-iqueryablet)
  - [19. `First`, `Single`, and `Any`](#19-first-single-and-any)
  - [20. Grouping, lookup, and duplicates](#20-grouping-lookup-and-duplicates)
  - [21. LINQ joins](#21-linq-joins)
  - [22. Delegates, `Action`, and `Func`](#22-delegates-action-and-func)
  - [23. Lambdas and closures](#23-lambdas-and-closures)
  - [24. Events](#24-events)
  - [25. Expression trees](#25-expression-trees)
  - [26. Pattern matching](#26-pattern-matching)
  - [27. Exceptions and exception flow](#27-exceptions-and-exception-flow)
  - [28. `IDisposable`, `IAsyncDisposable`, and ownership](#28-idisposable-iasyncdisposable-and-ownership)
  - [29. `Span<T>` and `ReadOnlySpan<T>`](#29-spant-and-readonlyspant)
  - [30. `Memory<T>` and `ReadOnlyMemory<T>`](#30-memoryt-and-readonlymemoryt)
  - [31. `stackalloc`](#31-stackalloc)
  - [32. `ArrayPool<T>`](#32-arraypoolt)
  - [33. Attributes](#33-attributes)
  - [34. Reflection fundamentals](#34-reflection-fundamentals)
  - [35. Source-generation fundamentals](#35-source-generation-fundamentals)
  - [36. Modern C# / C# 14 backend-relevant features](#36-modern-c-c-14-backend-relevant-features)
- [P0 — Async & Concurrency]
  - [37. `Task` and `Task<T>`](#37-task-and-taskt)
  - [38. `async` / `await`](#38-async-await)
  - [39. I/O-bound vs CPU-bound work](#39-io-bound-vs-cpu-bound-work)
  - [40. Sequential vs concurrent async work](#40-sequential-vs-concurrent-async-work)
  - [41. Cancellation and `CancellationToken`](#41-cancellation-and-cancellationtoken)
  - [42. Avoid sync-over-async](#42-avoid-sync-over-async)
  - [43. `async void`](#43-async-void)
  - [44. `Task<T>` vs `ValueTask<T>`](#44-taskt-vs-valuetaskt)
  - [45. `Task.WhenAll`](#45-taskwhenall)
  - [46. `Task.WhenAny`](#46-taskwhenany)
  - [47. Timeouts](#47-timeouts)
  - [48. Process vs thread vs task](#48-process-vs-thread-vs-task)
  - [49. Race conditions](#49-race-conditions)
  - [50. Atomicity and `Interlocked`](#50-atomicity-and-interlocked)
  - [51. `lock`](#51-lock)
  - [52. `SemaphoreSlim`](#52-semaphoreslim)
  - [53. Concurrent collections](#53-concurrent-collections)
  - [54. Deadlocks](#54-deadlocks)
  - [55. `Channel<T>`](#55-channelt)
  - [56. ThreadPool starvation](#56-threadpool-starvation)
  - [57. Concurrency vs parallelism](#57-concurrency-vs-parallelism)
  - [58. Bounded concurrency](#58-bounded-concurrency)
  - [59. `Parallel.ForEachAsync`](#59-parallelforeachasync)
  - [60. `IAsyncEnumerable<T>`](#60-iasyncenumerablet)
- [Appendix — Additional Material Taught That Belongs to P1 Runtime & Diagnostics](#appendix-additional-material-taught-that-belongs-to-p1-runtime-diagnostics)
  - [CLR, IL, and JIT](#clr-il-and-jit)
  - [Stack frames and object lifetime](#stack-frames-and-object-lifetime)
  - [Managed heap and GC reachability](#managed-heap-and-gc-reachability)
  - [GC generations](#gc-generations)
  - [Large Object Heap](#large-object-heap)
  - [Allocation pressure](#allocation-pressure)
  - [Managed memory leaks / retention](#managed-memory-leaks-retention)
- [Common Mistakes and Important Caveats](#common-mistakes-and-important-caveats)
  - [Category 1 — P0 Professional C# Fundamentals](#category-1-p0-professional-c-fundamentals)
  - [Category 1 — P0 Async & Concurrency](#category-1-p0-async-concurrency)
- [Roadmap Topics Partially Covered](#roadmap-topics-partially-covered)
  - [Category 1 — P0](#category-1-p0)
  - [Category 1 — P1 Runtime & Diagnostics](#category-1-p1-runtime-diagnostics)
- [Roadmap Topics Still Remaining](#roadmap-topics-still-remaining)
  - [Category 1 — P0](#category-1-p0)
  - [Category 1 — P1 Runtime & Diagnostics](#category-1-p1-runtime-diagnostics)

---

# P0 — Professional C# Fundamentals

## 1. Value types vs reference types

The important distinction is **semantics**, not simply “stack vs heap”.

### Value types

A value-type variable contains its value.

Common examples:

```csharp
int
bool
double
decimal
DateTime
Guid
enum
struct
record struct
```

Assignment copies the value:

```csharp
int a = 10;
int b = a;

b = 20;

// a == 10
// b == 20
```

### Reference types

A reference-type variable contains a reference to an object.

Common examples:

```csharp
class
record class
string
array
delegate
```

Example:

```csharp
var first = new Person { Name = "Alice" };
var second = first;

second.Name = "Bob";

// first.Name == "Bob"
// second.Name == "Bob"
```

Both variables refer to the same object.

### Important caveat: value type does not mean stack

This is an oversimplification:

```text
value type = stack
reference type = heap
```

A value type can be stored inside a heap-allocated object:

```csharp
public sealed class Player
{
    public int Score { get; set; }
}
```

A better mental model is:

```text
Value type     -> contains its data
Reference type -> contains a reference to an object
```

Storage location is a separate runtime concern.

---

## 2. Copying and parameter passing

### Reference assignment is not cloning

```csharp
var a = new Person();
var b = a;
```

This copies the reference, not the `Person` object.

```text
a ----\
       -> Person object
b ----/
```

### Struct assignment copies the value

```csharp
Point a = new(10, 20);
Point b = a;
```

`b` receives a copy of the struct.

Large structs can therefore be more expensive when copied repeatedly.

### Parameters are passed by value by default

That includes reference-type variables.

```csharp
void Rename(Person person)
{
    person.Name = "Bob";
}
```

The method receives a copy of the reference. Both references still point to the same object, so mutating the object is visible to the caller.

However:

```csharp
void Replace(Person person)
{
    person = new Person();
}
```

does not replace the caller's variable. Only the local copy of the reference changes.

### `ref`, `out`, and `in`

`ref` lets the method work with the caller's variable:

```csharp
void Replace(ref Person person)
{
    person = new Person();
}
```

`out` requires the called method to assign the value:

```csharp
if (int.TryParse(input, out int value))
{
    Console.WriteLine(value);
}
```

`in` passes by reference while preventing mutation through that parameter:

```csharp
void Process(in LargeStruct value)
{
}
```

Do not add `in` purely for assumed performance benefits. Measure first.

---

## 3. Boxing and unboxing

Boxing converts a value type into an object representation:

```csharp
int number = 10;
object boxed = number;
```

Unboxing extracts the value:

```csharp
int numberAgain = (int)boxed;
```

Generics avoid unnecessary boxing in many scenarios:

```csharp
List<int> numbers = new();
numbers.Add(10);
```

Older non-generic collections such as `ArrayList` operate through `object`, which can require boxing for value types.

---

## 4. `class`, `struct`, `record`, and `record struct`

### `class`

Use a class when identity and reference semantics matter.

```csharp
public sealed class Customer
{
    public Guid Id { get; init; }
    public string Name { get; set; } = "";
}
```

Two separate objects may contain identical property values while still representing different instances.

### `struct`

A struct is a value type.

```csharp
public struct Point
{
    public int X { get; set; }
    public int Y { get; set; }
}
```

Assignments copy the struct data.

Structs are generally best for relatively small, self-contained values with natural value semantics.

### `record class`

A record class remains a reference type but gets compiler-generated value-oriented behavior.

```csharp
public record Money(decimal Amount, string Currency);

var a = new Money(100m, "EUR");
var b = new Money(100m, "EUR");

Console.WriteLine(a == b); // True
```

Records are a strong fit where the contained values define logical equality.

### `record struct`

A record struct combines:

- value-type copy semantics
- compiler-generated value equality

```csharp
public readonly record struct Percentage(decimal Value);
```

### Identity-oriented entities vs value-oriented values

Use a normal class when identity remains stable while properties may change:

```text
Customer #42
Name changes
but it remains Customer #42
```

A record is more natural when the values define the concept:

```text
Money(100, EUR)
Coordinates(35.0, 24.0)
```

---

## 5. Equality and hashing

There are two different questions:

```text
Reference equality -> same object?
Value equality     -> same logical value?
```

### Reference equality

For a normal class without overloaded equality:

```csharp
var a = new Person { Name = "Alice" };
var b = new Person { Name = "Alice" };

Console.WriteLine(a == b); // False
```

Use:

```csharp
ReferenceEquals(a, b);
```

when you explicitly need object identity.

### `Equals` and `==`

`Equals` can be overridden.

`==` is type-specific and may also be overloaded.

Do not assume:

```text
== always means reference equality
```

For example, `string` and records use value-oriented equality.

### Hash-code contract

If:

```csharp
a.Equals(b) == true
```

then:

```csharp
a.GetHashCode() == b.GetHashCode()
```

must also be true.

The reverse is not required: unequal values may share a hash code.

This matters for:

```csharp
Dictionary<TKey, TValue>
HashSet<T>
```

### Mutable keys are dangerous

If the equality/hash code of a key depends on mutable state and that state changes after insertion, future lookups may search the wrong hash bucket.

Prefer stable keys such as:

```text
int
Guid
string
immutable value objects
```

### Record equality is not automatically deep equality

```csharp
public record Playlist(string Name, List<string> Tracks);
```

Two records containing two different `List<string>` instances with identical elements are not automatically equal.

Records compare their members using those members' own equality semantics.

---

## 6. Immutability, `readonly`, `init`, and `required`

### Immutability

An immutable object's observable state does not change after construction.

Benefits include:

- easier reasoning
- stable equality/hashing
- safer concurrent sharing
- good fit for value objects

### `readonly`

For a reference field:

```csharp
private readonly List<string> _items = new();
```

`readonly` prevents reassigning `_items` after construction, but does not prevent:

```csharp
_items.Add("A");
```

The reference is stable; the referenced object may still mutate.

### `init`

```csharp
public sealed class Person
{
    public string Name { get; init; } = "";
}
```

This allows initialization:

```csharp
var person = new Person
{
    Name = "Alice"
};
```

but prevents normal reassignment afterward.

### `required`

`required` means C# callers must initialize the member:

```csharp
public sealed class User
{
    public required string Name { get; init; }
}
```

This fails:

```csharp
var user = new User();
```

This works:

```csharp
var user = new User
{
    Name = "Alice"
};
```

### `required` and `init` are different

```text
required -> caller must initialize the member
init     -> assignment is restricted to initialization
```

They are often useful together.

### `required` does not guarantee non-null

`required` enforces assignment, not runtime validity.

Nullability analysis and validation are separate concerns.

### `SetsRequiredMembers`

A constructor can state that it establishes all required members:

```csharp
using System.Diagnostics.CodeAnalysis;

public sealed class User
{
    public required string Name { get; init; }

    [SetsRequiredMembers]
    public User(string name)
    {
        Name = name;
    }
}
```

Important caveat:

> `SetsRequiredMembers` is an assertion to the compiler. The compiler does not prove that all required members were actually initialized.

---

## 7. Nullable reference types and null-state analysis

Value types can use `Nullable<T>`:

```csharp
int? value = null;
```

Reference-type annotations:

```csharp
string name;
string? optionalName;
```

primarily provide compile-time nullability information.

```csharp
string? name = GetName();
Console.WriteLine(name.Length);
```

The compiler can warn that `name` may be null.

Important:

> `string?` is not a runtime `Nullable<string>` wrapper.

Nullability annotations are part of the API contract and compiler analysis.

---

## 8. Shallow vs deep copying

### Reference assignment

```csharp
var b = a;
```

does not clone an object.

### Shallow copy

A shallow copy creates a new outer object but reuses nested references.

Record `with` expressions are shallow:

```csharp
public record Order(string Number, List<string> Items);

var original =
    new Order("1", new List<string> { "A" });

var copy = original with
{
    Number = "2"
};

copy.Items.Add("B");

// original.Items also contains "B"
```

### Deep copy

A deep copy duplicates nested objects as required by the domain.

C# has no universal deep-clone operation because the correct meaning of “copy” depends on the model.

---

## 9. Interfaces and abstraction

An interface defines a contract:

```csharp
public interface IEmailSender
{
    Task SendAsync(
        string recipient,
        string subject,
        string body,
        CancellationToken cancellationToken);
}
```

Consumers can depend on the abstraction instead of the implementation.

### Why abstraction exists

Abstraction can:

- hide implementation details
- reduce coupling
- allow alternative implementations
- restrict the capabilities exposed to callers

Example:

```csharp
IReadOnlyList<User>
```

exposes reading/indexing without exposing list mutation through that interface.

### Avoid meaningless abstractions

Do not create an interface for every class by default.

Use an interface when it represents a meaningful contract, capability, boundary, or variation point.

---

## 10. Abstract classes, inheritance, composition, and polymorphism

### Abstract classes

An abstract class can combine:

- shared implementation/state
- required subclass behavior

```csharp
public abstract class NotificationSender
{
    public abstract Task SendAsync(string message);

    protected string Format(string message) =>
        $"[{DateTime.UtcNow:O}] {message}";
}
```

Common .NET abstract classes discussed:

```text
Stream
TextReader
TextWriter
DbConnection
HttpMessageHandler
BackgroundService
ControllerBase
```

### Inheritance

Inheritance should model a genuine **is-a** relationship.

### Composition

Composition models **has-a / uses-a**.

```csharp
public sealed class ReportService
{
    private readonly IFileStorage _storage;

    public ReportService(IFileStorage storage)
    {
        _storage = storage;
    }
}
```

Prefer composition when code reuse is the only reason you are considering inheritance.

### Polymorphism

Different implementations can be consumed through one abstraction.

```csharp
public interface IStorage
{
    Task SaveAsync(byte[] data);
}
```

### `virtual`, `override`, and `sealed`

```csharp
public class PriceCalculator
{
    public virtual decimal Calculate() => 100m;
}

public sealed class DiscountCalculator : PriceCalculator
{
    public override decimal Calculate() => 80m;
}
```

---

## 11. Access modifiers

The main modifiers discussed were:

```text
public
private
protected
internal
protected internal
private protected
```

General rule:

> Expose the smallest API surface callers genuinely need.

---

## 12. Generics

Generics let code work with different types while preserving compile-time type information.

```csharp
public sealed class Storage<T>
{
    public T Value { get; set; } = default!;
}
```

### Generic methods

```csharp
public static T GetFirst<T>(
    IEnumerable<T> values)
{
    return values.First();
}
```

### Multiple generic parameters

A method or type can have multiple type parameters:

```csharp
public void Process<TUser, TNetwork>(
    TUser user,
    TNetwork network)
{
}
```

Descriptive names are clearer than `T`, `K`, etc. when each parameter has a distinct role.

### Constraints

```csharp
public interface IEntity
{
    Guid Id { get; }
}

public void Save<T>(T entity)
    where T : IEntity
{
    Console.WriteLine(entity.Id);
}
```

Common constraints:

```csharp
where T : class
where T : struct
where T : IEntity
where T : new()
```

---

## 13. Variance

Suppose:

```csharp
class Animal { }
class Dog : Animal { }
```

### Covariance — `out`

```csharp
IEnumerable<Dog> dogs = GetDogs();
IEnumerable<Animal> animals = dogs;
```

Mnemonic:

```text
out -> produces T
```

### Contravariance — `in`

```csharp
Action<Animal> handleAnimal = animal => { };
Action<Dog> handleDog = handleAnimal;
```

Mnemonic:

```text
in -> consumes T
```

### Invariance

This is invalid:

```csharp
List<Dog> dogs = new();
List<Animal> animals = dogs;
```

Otherwise a caller could insert a non-`Dog` into the underlying `List<Dog>`.

---

## 14. Collection abstractions

### `IEnumerable<T>`

Promises enumeration.

It does not guarantee:

- indexing
- mutation
- materialization in memory

### `ICollection<T>`

Adds:

```text
Count
Add
Remove
Contains
Clear
```

### `IList<T>`

Adds indexed mutable access.

### `IReadOnlyCollection<T>`

Enumeration + `Count`, without mutation through the interface.

### `IReadOnlyList<T>`

Adds read-only indexing.

### `ISet<T>`

Represents uniqueness and set operations.

Typical implementation:

```csharp
HashSet<T>
```

### `IDictionary<TKey, TValue>`

Represents key/value lookup and mutation.

Read-only counterpart:

```csharp
IReadOnlyDictionary<TKey, TValue>
```

### Choosing an abstraction

Use the narrowest abstraction that provides the capabilities the consumer needs:

```text
Only enumerate       -> IEnumerable<T>
Need Count           -> IReadOnlyCollection<T>
Need indexing        -> IReadOnlyList<T>
Need mutation        -> ICollection<T> / IList<T>
Need key lookup      -> dictionary abstraction
```

---

## 15. Concrete collections

### `List<T>`

Good general-purpose ordered collection.

Searching by predicate is generally O(n):

```csharp
users.FirstOrDefault(x => x.Id == id);
```

### `Dictionary<TKey, TValue>`

Good for repeated lookup by key.

```csharp
if (usersById.TryGetValue(id, out var user))
{
}
```

Average lookup is typically O(1).

Prefer `TryGetValue` when you need both existence and the value.

### `HashSet<T>`

Good when uniqueness or repeated membership checks matter.

Average membership lookup is typically O(1).

### `Queue<T>` / `Stack<T>`

```text
Queue<T> -> FIFO
Stack<T> -> LIFO
```

---

## 16. LINQ fundamentals

LINQ expresses transformations and queries declaratively:

```csharp
var activeNames = users
    .Where(x => x.IsActive)
    .OrderBy(x => x.Name)
    .Select(x => x.Name);
```

Important operators discussed:

```text
Where
Select
OrderBy
ThenBy
First
FirstOrDefault
Single
SingleOrDefault
Any
Count
GroupBy
Distinct
DistinctBy
Join
GroupJoin
ToList
ToArray
ToDictionary
```

---

## 17. Deferred execution and materialization

Many LINQ queries do not execute when they are defined:

```csharp
var query =
    users.Where(x => x.IsActive);
```

They execute when enumerated or materialized:

```csharp
foreach (var user in query)
{
}
```

```csharp
var result = query.ToList();
```

### Multiple enumeration

```csharp
IEnumerable<User> users = GetUsers();

if (users.Any())
{
    foreach (var user in users)
    {
    }
}
```

may enumerate the source twice.

Whether that matters depends on what the sequence represents.

Materialize when you intentionally need a stable snapshot reused multiple times.

Do not call `ToList()` automatically without understanding the execution model.

---

## 18. `IEnumerable<T>` vs `IQueryable<T>`

These are abstractions; LINQ is what you perform on them.

### `IEnumerable<T>`

LINQ normally executes .NET code over a sequence:

```csharp
IEnumerable<User> users = list;

var filtered =
    users.Where(x => x.IsActive);
```

These operators come from `Enumerable`.

### `IQueryable<T>`

Represents a query a provider can inspect:

```csharp
IQueryable<User> users = querySource;

var filtered =
    users.Where(x => x.IsActive);
```

These operators come from `Queryable`.

Important:

> `IQueryable<T>` does not inherently mean SQL.

A provider interprets the expression tree. A relational ORM provider can translate supported expressions into SQL.

### Filter and project before materialization

Prefer:

```csharp
var users = await dbContext.Users
    .Where(x => x.IsActive)
    .Select(x => new UserDto(
        x.Id,
        x.Name))
    .ToListAsync();
```

over loading all entities and filtering in memory afterward.

---

## 19. `First`, `Single`, and `Any`

### `First`

Returns the first match and throws if none exists.

### `FirstOrDefault`

Returns the first match or default if none exists.

### `Single`

Requires exactly one matching item.

Throws if zero or multiple items match.

### `SingleOrDefault`

Allows zero or one match, but throws if multiple values match.

### `Any`

Use when the question is simply whether a match exists:

```csharp
bool exists =
    users.Any(x => x.IsActive);
```

Do not count all matching items just to test existence.

---

## 20. Grouping, lookup, and duplicates

### `GroupBy`

```csharp
var byCountry =
    users.GroupBy(x => x.Country);
```

### `ToLookup`

```csharp
var lookup =
    users.ToLookup(x => x.Country);
```

This is useful for one-key-to-many-values lookups.

### Removing duplicates

Use `Distinct()` for values considered equal:

```csharp
var unique =
    values.Distinct();
```

Use `DistinctBy` to deduplicate by a key:

```csharp
var uniqueUsers =
    users.DistinctBy(x => x.Id);
```

Use `GroupBy` when you want to group duplicates and decide how to aggregate or select:

```csharp
var result = users
    .GroupBy(x => x.Id)
    .Select(group => group.First());
```

Important caveat:

> Multiple rows from a one-to-many join are not automatically duplicates. They may represent genuinely different joined pairs.

---

## 21. LINQ joins

### Inner join

```csharp
var result =
    users.Join(
        departments,
        user => user.DepartmentId,
        department => department.Id,
        (user, department) => new
        {
            UserName = user.Name,
            DepartmentName = department.Name
        });
```

Only matching pairs are returned.

### Query syntax

```csharp
var result =
    from user in users
    join department in departments
        on user.DepartmentId equals department.Id
    select new
    {
        UserName = user.Name,
        DepartmentName = department.Name
    };
```

### `GroupJoin`

```csharp
var result =
    departments.GroupJoin(
        users,
        department => department.Id,
        user => user.DepartmentId,
        (department, departmentUsers) => new
        {
            Department = department,
            Users = departmentUsers
        });
```

Each outer item gets a sequence of matching inner items.

### Classic left-join pattern

```csharp
var result =
    from user in users
    join department in departments
        on user.DepartmentId equals department.Id
        into departmentGroup
    from department in departmentGroup.DefaultIfEmpty()
    select new
    {
        UserName = user.Name,
        DepartmentName =
            department == null
                ? null
                : department.Name
    };
```

### Provider-backed joins

For `IQueryable<T>`, a provider may translate a join expression into a database join.

Avoid materializing both sides before joining if the provider can perform the join.

### Navigation properties

When an ORM already models a relationship, using a navigation-property projection may be clearer than manually writing an explicit join.

---

## 22. Delegates, `Action`, and `Func`

A delegate is a strongly typed reference to executable behavior.

```csharp
public delegate int Operation(
    int a,
    int b);
```

### `Action`

Returns `void`:

```csharp
Action<string> print =
    message => Console.WriteLine(message);
```

### `Func`

Returns a value. The last generic parameter is the return type:

```csharp
Func<User, bool> isActive =
    user => user.IsActive;
```

This represents:

```text
User -> bool
```

---

## 23. Lambdas and closures

A lambda is concise anonymous behavior:

```csharp
user => user.IsActive
```

Its target context determines what it becomes.

### Closures

A lambda can capture variables from its surrounding scope:

```csharp
int minimumAge = 30;

var result =
    users.Where(x => x.Age >= minimumAge);
```

Captured variables are not frozen snapshots:

```csharp
int value = 10;

Func<int> getValue =
    () => value;

value = 20;

Console.WriteLine(getValue()); // 20
```

Be careful when captured state is mutable.

---

## 24. Events

Events build on delegates for publisher/subscriber communication.

```csharp
public sealed class Job
{
    public event Action? Completed;

    public void Complete()
    {
        Completed?.Invoke();
    }
}
```

External code can subscribe/unsubscribe but normally cannot raise the event.

Important caveat:

> A long-lived publisher can retain subscribers through event-handler references.

Also:

> A C# event is an in-process language mechanism. It is not a durable or distributed messaging system.

---

## 25. Expression trees

A delegate is executable code:

```csharp
Func<User, bool> predicate =
    x => x.Age > 30;
```

An expression tree describes code as data:

```csharp
Expression<Func<User, bool>> expression =
    x => x.Age > 30;
```

Conceptually:

```text
Lambda
  └─ GreaterThan
      ├─ MemberAccess: Age
      └─ Constant: 30
```

This is why a query provider can inspect an expression.

### `IEnumerable<T>`

A lambda normally becomes executable .NET behavior.

### `IQueryable<T>`

A lambda normally becomes an expression tree the provider can inspect and potentially translate.

### Compiling an expression tree

```csharp
Func<User, bool> predicate =
    expression.Compile();
```

An arbitrary compiled delegate does not generally preserve the original high-level expression-tree structure.

### Provider limitation

Two separate questions matter:

```text
Can C# represent this as an expression tree?
Can this provider translate that expression?
```

A custom method call can be representable while still being unsupported by a query provider.

---

## 26. Pattern matching

### Type patterns

```csharp
if (value is User user)
{
    Console.WriteLine(user.Name);
}
```

### Null patterns

```csharp
if (user is null)
{
}

if (user is not null)
{
}
```

### Property patterns

```csharp
if (order is
    {
        Status: OrderStatus.Ready,
        IsActive: true
    })
{
}
```

### Relational and logical patterns

```csharp
if (age is >= 18 and < 65)
{
}
```

Available combinators include:

```text
and
or
not
```

### `switch` expressions

```csharp
string Describe(Status status) =>
    status switch
    {
        Status.Draft => "Draft",
        Status.Published => "Published",
        _ => "Unknown"
    };
```

### `when` guards

```csharp
return value switch
{
    Item item when CanProcess(item)
        => Result.Allowed,

    _ => Result.NotAllowed
};
```

Use pattern matching where it improves the model of the decision, not merely because the syntax is newer.

---

## 27. Exceptions and exception flow

Exceptions propagate up the call stack until handled.

Catch exceptions when you can:

- recover
- translate
- add useful context
- handle them at an application boundary

Avoid swallowing exceptions:

```csharp
try
{
    await SaveAsync();
}
catch (Exception)
{
    // failure disappears
}
```

### `finally`

`finally` runs when control leaves the `try`, including on exceptions and normal returns.

### `throw` vs `throw ex`

When simply rethrowing the current exception:

```csharp
catch (Exception)
{
    throw;
}
```

preserves the original stack-trace context.

Avoid:

```csharp
catch (Exception ex)
{
    throw ex;
}
```

when your intention is just to rethrow.

### Wrapping exceptions

```csharp
try
{
    await SaveAsync();
}
catch (IOException ex)
{
    throw new StorageException(
        "The item could not be stored.",
        ex);
}
```

The original exception remains available as `InnerException`.

### Exception filters

```csharp
catch (HttpRequestException ex)
    when (ex.StatusCode == HttpStatusCode.NotFound)
{
    return null;
}
```

### Do not use exceptions for expected control flow

Prefer:

```csharp
int.TryParse(input, out var value);
```

when invalid input is expected.

---

## 28. `IDisposable`, `IAsyncDisposable`, and ownership

The GC manages managed memory. It does not replace deterministic cleanup of external/scarce resources.

Resources that can require prompt cleanup include:

- file handles
- streams
- sockets
- database-related resources
- native handles

### `IDisposable`

```csharp
using var stream =
    File.OpenRead(path);
```

`Dispose()` releases the owned resource.

It does **not** mean “free this managed object immediately”.

### `using` statement

```csharp
using (var stream = File.OpenRead(path))
{
    Process(stream);
}
```

### `IAsyncDisposable`

```csharp
await using var resource =
    await CreateResourceAsync();
```

This eventually calls:

```csharp
await resource.DisposeAsync();
```

Mental model:

```text
GC                     -> managed-memory reclamation
Dispose / DisposeAsync -> deterministic resource cleanup
```

---

## 29. `Span<T>` and `ReadOnlySpan<T>`

`Span<T>` is a view over contiguous memory.

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };

Span<int> middle =
    numbers.AsSpan(1, 3);
```

No new array is created.

Mutating the span mutates the underlying data:

```csharp
middle[0] = 100;

Console.WriteLine(numbers[1]); // 100
```

`ReadOnlySpan<T>` provides a read-only view.

```csharp
ReadOnlySpan<char> id =
    "ITEM-12345".AsSpan(5, 5);
```

This avoids creating a substring when only a view is needed.

### Lifetime restrictions

`Span<T>` is a `ref struct`.

It cannot be stored as a field in a normal class.

Beginning with C# 13, `ref struct` locals can be used in async methods under ref-safety rules, but they cannot remain live across an `await` suspension point. The compiler enforces these lifetime restrictions.

---

## 30. `Memory<T>` and `ReadOnlyMemory<T>`

`Memory<T>` is a storable, async-friendly representation of memory.

```csharp
public async Task ProcessAsync(
    Memory<byte> buffer)
{
    await PrepareAsync();

    Process(buffer.Span);
}
```

Useful mental model:

```text
Memory<T> -> can be stored and passed across async boundaries
Span<T>   -> synchronous view used while accessing the data
```

Read-only counterparts:

```text
ReadOnlyMemory<T>
ReadOnlySpan<T>
```

---

## 31. `stackalloc`

A span can point at stack-allocated memory:

```csharp
Span<int> values =
    stackalloc int[10];
```

That storage has stack lifetime, which is one reason the compiler enforces strict escape/lifetime rules.

---

## 32. `ArrayPool<T>`

`ArrayPool<T>` reduces repeated temporary array allocation by renting reusable arrays.

```csharp
byte[] buffer =
    ArrayPool<byte>.Shared.Rent(4096);

try
{
    // use buffer
}
finally
{
    ArrayPool<byte>.Shared.Return(buffer);
}
```

Important rules:

```text
Rent(4096)
    -> array length is at least 4096

Rented array
    -> may contain old data

Return(buffer)
    -> ownership returns to the pool
```

Never use a rented buffer after returning it.

For sensitive data:

```csharp
pool.Return(
    buffer,
    clearArray: true);
```

can request clearing before reuse.

Relationship:

```text
ArrayPool<T> -> reduces repeated array allocation
Span<T>      -> reduces copying / enables efficient slicing
```

---

## 33. Attributes

Attributes attach metadata to code.

```csharp
[Audit]
public void Process()
{
}
```

An attribute derives from `System.Attribute`.

```csharp
public sealed class AuditAttribute : Attribute
{
}
```

### Attributes can carry values

```csharp
public sealed class MaxRetriesAttribute : Attribute
{
    public int Count { get; }

    public MaxRetriesAttribute(int count)
    {
        Count = count;
    }
}
```

Usage:

```csharp
[MaxRetries(3)]
public void Process()
{
}
```

### `AttributeUsage`

```csharp
[AttributeUsage(
    AttributeTargets.Class |
    AttributeTargets.Method)]
public sealed class AuditAttribute : Attribute
{
}
```

Attributes normally describe metadata.

They do not automatically execute behavior; framework/runtime/generated infrastructure must inspect the metadata and act on it.

---

## 34. Reflection fundamentals

Reflection lets code inspect .NET metadata at runtime.

### `typeof`

```csharp
Type type =
    typeof(User);
```

### `GetType`

```csharp
Animal animal =
    new Dog();

Type type =
    animal.GetType(); // Dog
```

`typeof(Animal)` refers to a statically named type.

`animal.GetType()` returns the actual runtime type.

### Inspecting members

```csharp
PropertyInfo[] properties =
    typeof(User).GetProperties();

MethodInfo[] methods =
    typeof(User).GetMethods();
```

### Reading attributes

```csharp
bool audited =
    typeof(Service).IsDefined(
        typeof(AuditAttribute),
        inherit: true);
```

### Dynamic access

Reflection can read/set members and invoke methods dynamically.

Trade-offs:

- runtime overhead
- weaker compile-time safety
- string/member-name mistakes become runtime issues
- more difficulty for trimming/AOT analysis

Prefer strongly typed code when type relationships are already known.

Use reflection when runtime discovery is genuinely part of the problem.

---

## 35. Source-generation fundamentals

A source generator inspects compilation information at build time and emits additional C# source that participates in the same compilation.

Conceptually:

```text
Your source
   +
source generator
   |
generated .cs
   |
compiler
   |
assembly
```

### Reflection vs source generation

```text
Reflection
    -> discover information at runtime

Source generation
    -> inspect code at compile time
    -> generate additional code
```

Common motivations:

- reduce runtime reflection
- improve Native AOT/trimming compatibility
- generate repetitive boilerplate
- shift work from runtime to build time

### Incremental generators

Modern generators usually use an incremental model so the compiler can recompute only affected parts of the generator pipeline.

At P0 level, recognizing the model and why libraries use it is more important than implementing an advanced Roslyn generator.

---

## 36. Modern C# / C# 14 backend-relevant features

C# 14 is supported on .NET 10.

The C# 14 features discussed were:

### `field`-backed properties

`field` lets an accessor use the compiler-generated backing field:

```csharp
public string Email
{
    get;
    set => field =
        value?.Trim().ToLowerInvariant() ?? "";
}
```

### Null-conditional assignment

```csharp
customer?.Order = currentOrder;
```

The right-hand side is evaluated only when the receiver is non-null.

### Extension members

C# 14 extension blocks expand extension functionality beyond traditional extension methods, including extension properties and additional member forms.

### Improved span conversions

C# 14 adds more implicit conversions involving:

```text
T[]
Span<T>
ReadOnlySpan<T>
```

### Simple lambda parameters with modifiers

Modifiers such as `ref`, `in`, and `out` can be used on simple lambda parameters without explicitly typing every parameter.

### `nameof` with unbound generic types

```csharp
nameof(List<>)
```

produces:

```text
List
```

### More partial members

C# 14 adds partial constructors and partial events, which is particularly useful in generated-code scenarios.

---

# P0 — Async & Concurrency

## 37. `Task` and `Task<T>`

A `Task` represents an operation that may complete later.

```csharp
Task SaveAsync();
Task<User> GetUserAsync();
```

`Task<T>` eventually produces a value:

```csharp
User user =
    await GetUserAsync();
```

A task is not the same thing as a thread.

---

## 38. `async` / `await`

An async method executes synchronously until it reaches an `await` whose operation is not already complete.

Conceptually:

```text
execute normally
     |
reach incomplete await
     |
save continuation/state
     |
return control
     |
operation completes
     |
resume continuation
```

The compiler implements async methods using a state-machine transformation.

### Async does not mean “new thread”

For asynchronous I/O, no dedicated thread normally needs to remain blocked simply waiting for the external resource.

This is why async is valuable for:

- database I/O
- HTTP calls
- file I/O
- sockets
- other network operations

---

## 39. I/O-bound vs CPU-bound work

### I/O-bound

Most time is spent waiting:

```csharp
await httpClient.GetAsync(url);
await stream.ReadAsync(buffer);
```

Use asynchronous APIs where available.

### CPU-bound

The CPU is actively doing work:

```csharp
CalculateLargeMatrix();
```

Marking a method `async` does not make CPU work cheaper.

### `Task.Run`

```csharp
var result =
    await Task.Run(
        ExpensiveCalculation);
```

schedules work on the ThreadPool.

In server-side code, do not wrap normal asynchronous I/O in `Task.Run` just to make it appear asynchronous.

---

## 40. Sequential vs concurrent async work

Sequential:

```csharp
var user =
    await GetUserAsync();

var orders =
    await GetOrdersAsync();
```

Concurrent:

```csharp
Task<User> userTask =
    GetUserAsync();

Task<List<Order>> ordersTask =
    GetOrdersAsync();

await Task.WhenAll(
    userTask,
    ordersTask);
```

Only overlap operations that are independent and whose dependencies support concurrent use.

---

## 41. Cancellation and `CancellationToken`

Cancellation is cooperative.

```csharp
public async Task<User?> GetUserAsync(
    Guid id,
    CancellationToken cancellationToken)
{
    return await repository.GetAsync(
        id,
        cancellationToken);
}
```

Propagate the token down the call chain when supported.

For CPU loops:

```csharp
cancellationToken.ThrowIfCancellationRequested();
```

can be used at suitable checkpoints.

A token does not forcibly terminate arbitrary code.

---

## 42. Avoid sync-over-async

Avoid:

```csharp
var user =
    GetUserAsync().Result;
```

and:

```csharp
GetUserAsync().Wait();
```

Prefer:

```csharp
var user =
    await GetUserAsync();
```

Blocking asynchronous work wastes threads and can contribute to:

- deadlocks in synchronization-context environments
- ThreadPool starvation in server applications

---

## 43. `async void`

Avoid for normal asynchronous methods:

```csharp
public async void Save()
{
}
```

Prefer:

```csharp
public async Task SaveAsync()
{
}
```

A `Task` lets callers:

- await completion
- observe exceptions
- compose the operation

`async void` is mainly appropriate for event-handler shapes.

---

## 44. `Task<T>` vs `ValueTask<T>`

`Task<T>` is a reference-type object representing an asynchronous operation.

`ValueTask<T>` is a value type that can represent:

- an already available result
- a `Task<T>`
- an `IValueTaskSource<T>`-backed operation

A synchronous fast path can sometimes avoid allocating a separate `Task<T>` object.

### Why `ValueTask<T>` is more complex

As a safe consumer rule, treat a `ValueTask<T>` as single-consumption unless the API explicitly documents otherwise.

Do not assume it is safe to:

- await it multiple times
- await it concurrently
- call `AsTask()` multiple times
- mix consumption patterns

If reusable task semantics are needed:

```csharp
Task<User> task =
    valueTask.AsTask();
```

but doing so can remove part of the allocation advantage.

### Practical rule

Default to:

```text
Task
Task<T>
```

Use `ValueTask<T>` when:

- synchronous completion is common
- the code path is hot
- allocation reduction matters
- measurement justifies the extra API complexity

---

## 45. `Task.WhenAll`

`Task.WhenAll` completes when all supplied tasks complete.

```csharp
await Task.WhenAll(
    firstTask,
    secondTask);
```

Good for a small or controlled set of independent operations.

Be careful when generating an enormous number of tasks from a very large collection; that can create excessive concurrency.

---

## 46. `Task.WhenAny`

`Task.WhenAny` completes when the first supplied task completes:

```csharp
Task winner =
    await Task.WhenAny(
        operation,
        timeoutTask);
```

Important:

> `WhenAny` returns the first task to complete, not necessarily the first task to succeed.

You still need to await the returned task to observe its result or exception.

Also:

> `WhenAny` does not cancel the losing tasks.

---

## 47. Timeouts

Timeout and cancellation are related but different:

```text
Timeout      -> allowed duration exceeded
Cancellation -> caller/system requests stop
```

### `CancelAfter`

```csharp
using var cts =
    new CancellationTokenSource();

cts.CancelAfter(
    TimeSpan.FromSeconds(5));

await DoWorkAsync(cts.Token);
```

### Linked cancellation

```csharp
using var timeoutCts =
    new CancellationTokenSource(
        TimeSpan.FromSeconds(5));

using var linkedCts =
    CancellationTokenSource
        .CreateLinkedTokenSource(
            callerToken,
            timeoutCts.Token);

await DoWorkAsync(
    linkedCts.Token);
```

Now either the caller or the timeout can request cancellation.

### `WaitAsync`

```csharp
await task.WaitAsync(
    TimeSpan.FromSeconds(5));
```

provides a convenient timeout while waiting.

Important:

> Timing out the wait does not automatically cancel the underlying operation.

If the underlying operation should stop, pass an appropriate cancellation token into it.

---

## 48. Process vs thread vs task

```text
Process -> application instance / address space
Thread  -> execution path inside a process
Task    -> .NET abstraction representing an operation
```

A task may represent:

- ThreadPool work
- asynchronous I/O
- an already-completed operation

---

## 49. Race conditions

A race occurs when the result depends on timing between concurrent operations.

```csharp
private int _count;

public void Increment()
{
    _count++;
}
```

`_count++` is conceptually:

```text
read
add
write
```

Two threads can read the same old value and overwrite each other's update.

---

## 50. Atomicity and `Interlocked`

For simple atomic operations:

```csharp
Interlocked.Increment(
    ref _count);
```

Other APIs include:

```text
Interlocked.Decrement
Interlocked.Exchange
Interlocked.CompareExchange
```

Use `Interlocked` for small atomic operations, not arbitrary multi-step business invariants.

---

## 51. `lock`

Use `lock` for synchronous mutual exclusion:

```csharp
private readonly object _sync = new();

lock (_sync)
{
    if (_balance >= amount)
    {
        _balance -= amount;
    }
}
```

Protect the entire invariant.

Do not `await` inside a normal `lock`.

---

## 52. `SemaphoreSlim`

`SemaphoreSlim` supports async-compatible coordination:

```csharp
private readonly SemaphoreSlim _gate =
    new(1, 1);

public async Task ProcessAsync()
{
    await _gate.WaitAsync();

    try
    {
        await DoWorkAsync();
    }
    finally
    {
        _gate.Release();
    }
}
```

With a higher count:

```csharp
new SemaphoreSlim(5, 5);
```

it can implement bounded concurrency.

---

## 53. Concurrent collections

Examples:

```text
ConcurrentDictionary<TKey, TValue>
ConcurrentQueue<T>
ConcurrentStack<T>
ConcurrentBag<T>
```

A concurrent collection makes its supported operations thread-safe.

It does not make arbitrary multi-step logic automatically thread-safe.

Example:

```csharp
var value =
    cache.GetOrAdd(
        key,
        CreateValue);
```

Important caveat:

> Under contention, a `ConcurrentDictionary` value factory can be invoked more than once even though only one value becomes associated with the key.

Avoid non-idempotent side effects inside the factory unless repeated execution is acceptable.

---

## 54. Deadlocks

Classic deadlock:

```text
Thread A:
  owns lock A
  waits for lock B

Thread B:
  owns lock B
  waits for lock A
```

Consistent lock ordering is one prevention technique.

Deadlocks can also involve:

- blocking async code
- databases
- distributed synchronization
- synchronous waits

---

## 55. `Channel<T>`

`Channel<T>` is an async producer/consumer queue.

```text
Producer(s)
    |
Channel<T>
    |
Consumer(s)
```

### Writer and reader

```text
ChannelWriter<T> -> producer side
ChannelReader<T> -> consumer side
```

### Unbounded channel

```csharp
var channel =
    Channel.CreateUnbounded<Job>();
```

Simple, but producers can outpace consumers and grow memory usage.

### Bounded channel

```csharp
var channel =
    Channel.CreateBounded<Job>(100);
```

Bounded channels provide backpressure.

The default full mode is `Wait`, where `WriteAsync` asynchronously waits for capacity.

Other full modes include:

```text
DropWrite
DropOldest
DropNewest
```

### Producer

```csharp
await writer.WriteAsync(job);
```

### Consumer

```csharp
await foreach (
    Job job in reader.ReadAllAsync())
{
    await ProcessAsync(job);
}
```

### Completion

```csharp
writer.Complete();
```

signals that no more items will be written.

### Important limitation

A normal channel is in-process memory.

It is not a replacement for a durable/distributed message broker.

---

## 56. ThreadPool starvation

ThreadPool starvation occurs when worker threads are blocked or occupied faster than they become available, so queued work waits too long to run.

Common causes:

```text
.Result
.Wait()
blocking waits
synchronous I/O under load
excessive Task.Run
```

### Why async helps

Blocking:

```text
thread starts I/O
thread waits blocked
I/O finishes
thread continues
```

Async:

```text
thread starts I/O
thread returns to pool
I/O finishes
continuation is scheduled
```

### Starvation vs CPU saturation

CPU saturation:

```text
CPU ~ 100%
```

ThreadPool starvation may show:

- high latency
- growing worker-thread count
- queued work
- CPU still below saturation

Main prevention:

- use true async I/O
- avoid sync-over-async
- avoid unnecessary blocking
- avoid uncontrolled CPU-heavy ThreadPool work

---

## 57. Concurrency vs parallelism

### Concurrency

Multiple operations make progress during overlapping periods.

```csharp
Task first =
    CallApiAAsync();

Task second =
    CallApiBAsync();

await Task.WhenAll(
    first,
    second);
```

### Parallelism

Multiple operations literally execute at the same time, usually on multiple CPU cores.

```text
Core 1 -> Work A
Core 2 -> Work B
Core 3 -> Work C
```

Async I/O is often concurrent without being CPU-parallel.

---

## 58. Bounded concurrency

Bounded concurrency limits how many operations are active at once.

This protects:

- CPU
- memory
- sockets
- database connection pools
- downstream APIs
- rate limits

Mechanisms discussed:

```text
SemaphoreSlim
Parallel.ForEachAsync
bounded Channel<T>
```

More concurrency is not automatically more performance.

---

## 59. `Parallel.ForEachAsync`

Use it to process a sequence concurrently with a controlled degree of parallelism/concurrency.

```csharp
var options =
    new ParallelOptions
    {
        MaxDegreeOfParallelism = 8,
        CancellationToken =
            cancellationToken
    };

await Parallel.ForEachAsync(
    items,
    options,
    async (item, ct) =>
    {
        await ProcessAsync(
            item,
            ct);
    });
```

Without an explicit `ParallelOptions` limit, the standard overload executes at most `Environment.ProcessorCount` operations in parallel.

### `Task.WhenAll` vs `Parallel.ForEachAsync`

```text
Small known set of tasks
    -> Task.WhenAll

Large sequence + explicit concurrency bound
    -> Parallel.ForEachAsync
       or another bounded-concurrency design
```

### CPU-bound work

A concurrency level near available CPU capacity is often a sensible starting point.

### I/O-bound work

A higher limit can sometimes be useful because operations spend much of their time waiting, but the correct value depends on downstream limits.

### Important dependency caveat

Do not run concurrent operations against a dependency that does not support concurrent use.

---

## 60. `IAsyncEnumerable<T>`

`IAsyncEnumerable<T>` represents an asynchronously produced sequence.

Producer:

```csharp
public async IAsyncEnumerable<int>
    GenerateAsync()
{
    for (int i = 0; i < 3; i++)
    {
        await Task.Delay(10);
        yield return i;
    }
}
```

Consumer:

```csharp
await foreach (
    var value in GenerateAsync())
{
    Console.WriteLine(value);
}
```

Compare:

```text
Task<List<T>>
    -> wait for the full collection

IAsyncEnumerable<T>
    -> consume incrementally
```

Useful for streaming and large/long-running sequences.

---

# Appendix — Additional Material Taught That Belongs to P1 Runtime & Diagnostics

The following material was taught in this chat, but the canonical roadmap classifies it under **P1**, not P0.

## CLR, IL, and JIT

C# normally compiles to IL plus metadata.

```text
C# source
   |
C# compiler
   |
IL + metadata
   |
assembly
```

The CLR provides runtime services such as:

- JIT compilation
- garbage collection
- exception handling
- assembly/type loading
- threading/runtime services
- managed/unmanaged interop

The JIT translates IL into native machine code for the current platform.

```text
IL
 |
JIT
 |
native machine code
 |
CPU
```

The JIT can also optimize code.

Tiered compilation lets the runtime balance quick initial compilation against stronger optimization for frequently executed methods.

---

## Stack frames and object lifetime

Method calls create execution frames.

A local variable can disappear when a method returns while the referenced object remains alive if some other reachable reference still points to it.

Therefore:

```text
variable lifetime != object lifetime
```

---

## Managed heap and GC reachability

Reference-type objects are normally allocated on the managed heap.

An object remains alive while it is reachable from a GC root.

```text
GC root
   |
Object A
   |
Object B
```

If `B` is reachable through `A`, it remains alive.

When no root can reach an object, it becomes eligible for garbage collection.

Eligible does not mean immediately reclaimed.

---

## GC generations

Simplified model:

```text
new object
   |
 Gen 0
   |
 survives
   |
 Gen 1
   |
 survives
   |
 Gen 2
```

The generational design is based on the observation that many objects are short-lived.

---

## Large Object Heap

Large managed allocations are treated differently and can be placed on the Large Object Heap (LOH).

This matters especially for:

- large arrays
- buffers
- files
- serialized payloads
- image/binary workloads

---

## Allocation pressure

Managed allocation can be inexpensive.

The bigger performance issue can be sustained allocation rate:

```text
many allocations
      |
GC pressure
      |
more collections
      |
CPU / pause cost
```

Do not remove every allocation automatically.

Measure before optimizing.

---

## Managed memory leaks / retention

A garbage-collected application can still retain memory unintentionally.

Example:

```csharp
public static readonly List<User> Users = new();
```

If objects are continually added and never removed, they remain reachable.

The GC cannot collect reachable objects.

Common retention sources discussed:

- static collections
- unbounded caches
- long-lived object graphs
- event subscriptions from long-lived publishers

---

# Common Mistakes and Important Caveats

1. Do not use “value type = stack, reference type = heap” as the core mental model.
2. Assigning a reference variable does not clone the object.
3. C# passes parameters by value by default, including references.
4. Do not choose records merely because they are newer than classes.
5. Record equality is not automatically deep equality.
6. Equal values must produce equal hash codes.
7. Avoid mutable hash keys when mutable members participate in equality.
8. `readonly`, `init`, and read-only interfaces do not make nested objects immutable.
9. `required` is not runtime validation and does not itself guarantee non-null data.
10. Prefer composition over inheritance unless a genuine “is-a” relationship exists.
11. Do not create an interface for every class automatically.
12. `IQueryable<T>` is an abstraction; LINQ is what you perform on it.
13. `IQueryable<T>` does not inherently mean SQL.
14. Materializing a provider-backed query too early can move filtering into application memory.
15. Deferred LINQ sequences may execute more than once if enumerated repeatedly.
16. One-to-many join output is not automatically duplicate data.
17. Use `Distinct`, `DistinctBy`, or `GroupBy` according to the equality/key semantics you want.
18. Do not swallow exceptions without meaningfully handling them.
19. Use `throw;`, not `throw ex;`, when simply rethrowing the current exception.
20. `Dispose` is resource cleanup, not manual garbage collection.
21. Async does not mean “run on a new thread”.
22. Do not wrap asynchronous I/O in `Task.Run` just to make it asynchronous.
23. Avoid `.Result` and `.Wait()` in async call chains.
24. Default to `Task` / `Task<T>`; use `ValueTask<T>` only where justified.
25. Treat a `ValueTask<T>` as single-consumption unless documented otherwise.
26. `Task.WhenAny` does not cancel losing tasks.
27. Timing out a wait does not automatically cancel the underlying operation.
28. Do not `await` inside a normal `lock`.
29. Concurrent collections do not make arbitrary multi-step logic automatically thread-safe.
30. `ConcurrentDictionary` value factories can execute more than once under contention.
31. `Span<T>` is a view, not an owner of memory.
32. A `Span<T>` / other `ref struct` must obey ref-safety rules and must not remain live across an `await` suspension point.
33. A rented `ArrayPool<T>` buffer may be larger than requested and may contain old data.
34. Never use a pooled array after returning it.
35. Attributes describe metadata; they do not execute behavior by themselves.
36. Reflection is powerful but should not replace strongly typed code when type relationships are already known.
37. Source generation adds code at compile time; it does not simply rewrite arbitrary source files in place.
38. An unbounded `Channel<T>` can grow indefinitely if producers outpace consumers.
39. ThreadPool starvation and CPU saturation are different problems.
40. More concurrency is not automatically more throughput.

---


# Roadmap Topics Partially Covered

## Category 1 — P0

At the intended roadmap depth, there are no known Category 1 P0 topics still only partially covered.

Several topics can later be explored at more advanced depth, including:

- advanced null-state annotations
- complex expression-tree construction
- advanced Roslyn/source-generator implementation
- low-level ref-safety and span rules
- lock-free algorithms
- detailed ThreadPool and scheduler internals

These are beyond the current P0 scope.

## Category 1 — P1 Runtime & Diagnostics

Partially covered:

- CLR architecture fundamentals
- IL / JIT
- stack vs managed heap
- object lifetime / GC roots
- GC generations
- Large Object Heap fundamentals
- allocation-pressure fundamentals
- managed memory-retention/leak concepts

---

# Roadmap Topics Still Remaining

## Category 1 — P1 Runtime & Diagnostics

Still remaining:

- finalization in detail
- Server GC
- runtime counters
- `dotnet-counters`
- `dotnet-trace`
- `dotnet-dump`
- `dotnet-gcdump`
- memory-dump analysis
- allocation profiling
- BenchmarkDotNet
- correct benchmarking methodology
