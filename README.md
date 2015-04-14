# .NET-EF6-PrecisionAnnotation
A custom annotation for Entity Framework which allows you to specify decimal precision on a property. 

##USAGE
1. Add the Precision.cs file to your data project and set the proper namespace
2. In your Entity Framework Context OnModelBuilder function, call the Precision.ConfigureModelBuilder() method

    ```csharp
    protected override void OnModelCreating(DbModelBuilder modelBuilder)
    {
        base.OnModelCreating(modelBuilder);
    
        // Precision attribute for decimals
        Precision.ConfigureModelBuilder(modelBuilder);
    }
    ```

3. Apply the annotation to your decimal properties in your code first models
    ```csharp
    [Precision(18,4)]
    public decimal quantity { get; set; }
    ```
