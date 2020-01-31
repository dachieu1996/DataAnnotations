# DataAnnotations

## Table
```csharp
Tables[Table(“tbl_Course”, Schema = “catalog”)]
public class Course
{
}
```

## Columns
```csharp
[Column(“sName”, TypeName = “varchar”)]
[Required]
[MaxLength(255)]
public string Name { get; set; }
```

## Primary Keys
```csharp
[Key]
[DatabaseGenerated(DatabaseGeneratedOption.None)]
public class Isbn { get; set; }
```

## Composite Primary Keys
```csharp
public class OrderItem
{
  [Key]
  [Column(Order = 1)]
  public int OrderId { get; set; }

  [Key]
  [Column(Order = 2)]
  public int OrderItemId { get; set; }
}
```

## Indices
```csharp
[Index]
public int AuthorId { get; set; }

[Index(IsUnique = true)]
public string Name { get; set; }
```

## Composite Indices
```csharp
[Index(“IX_AuthorStudentsCount”, 1)]
public int AuthorId { get; set; }

[Index(“IX_AuthorStudentsCount”, 2)]
public int StudentsCount { get; set; }
```

## Foreign Keys
```csharp
public class Course
{
  [ForeignKey(“Author”)]
  public int AuthorId { get; set; }

  public Author Author { get; set; }
}
```

