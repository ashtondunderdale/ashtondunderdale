```csharp
class SoftwareDeveloper
{
    public string Name { get; set; } = "Ashton Dunderdale";
    public string Role { get; set; } = "Junior Software Developer";

    public void Hi()
    {
        Console.WriteLine($"Hello, I'm {Name}, {Role}.");
    }

    static void Main(string[] args)
    {
        SoftwareDeveloper developer = new();
        developer.Hi();
    }
}
```

