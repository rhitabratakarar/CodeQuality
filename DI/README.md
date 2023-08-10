# Dependency Injection

### Theory:

A class should not directly create instances of another class it depends on; 

**For example:**

```csharp
// ClassA.cs
class ClassA: IClassA
{
		// STRICTLY AVOID THIS.
    public void UseDependency()
    {
				ClassB objectB = new ClassB();  // creating high coupled code
				objectB.Method();
    }
}
```

Instead, the "to-be-used class" `(class B)` is injected by the DI container.

```csharp
// ClassA.cs
class ClassA: IClassA
{
    private readonly IClassB _instanceB;

		// constructor dependency injection
    public Client(IClassB injectedInstance)
    {
        this._instanceB = injectedInstance;
    }
    public void UseDependency()
    {
        this._instanceB.Method();
    }
}

```

```csharp
// ClassB.cs
internal class ClassB: IClassB
{
    public void Method()
    {
        Console.WriteLine("ClassB.Method() invoked.");
    }
}
```

```csharp
// The DI Container ( Assume: ClassC )
IClassB classB = new ClassB();

// the dependency injection in action.
IClassA classA = new IClassA(classB);

classA.UseDependency();
```

The approach can be considered like this:

- Class A needs to call Class B.
- Instead of calling that Class B directly from Class A, use a DI container to inject that class.

**Benefits:**

This creates low coupled code that is easier to maintain and extend. 

**Note:** Try to program to interfaces instead of direct classes. This is called Dependency Inversion (an enabler of Dependency Injection) and hence increases the amount of possibilities that the code can use.

**Reference:**

[Dependency Injection](https://github.com/rhitabratakarar/Practice/tree/main/DependencyInjection)
