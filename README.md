# DataAnnotations

## Table
<pre>
Tables[Table(“tbl_Course”, Schema = “catalog”)]
public class Course
{
}
</pre>

## Columns
<pre>
[Column(“sName”, TypeName = “varchar”)]
[Required]
[MaxLength(255)]
public string Name { get; set; }
</pre>

## Primary Keys
<pre>
[Key]
[DatabaseGenerated(DatabaseGeneratedOption.None)]
public class Isbn { get; set; }
</pre>

## Composite Primary Keys
<pre>
public class OrderItem
{
  [Key]
  [Column(Order = 1)]
  public int OrderId { get; set; }

  [Key]
  [Column(Order = 2)]
  public int OrderItemId { get; set; }
}
</pre>

## Indices
<pre>
[Index]
public int AuthorId { get; set; }

[Index(IsUnique = true)]
public string Name { get; set; }
</pre>

## Composite Indices
<pre>
[Index(“IX_AuthorStudentsCount”, 1)]
public int AuthorId { get; set; }

[Index(“IX_AuthorStudentsCount”, 2)]
public int StudentsCount { get; set; }
</pre>

## Foreign Keys
<pre>
public class Course
{
  [ForeignKey(“Author”)]
  public int AuthorId { get; set; }

  public Author Author { get; set; }
}
</pre>

