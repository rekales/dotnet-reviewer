---
title: VB.NET Reviewer Guide
layout: home
nav_order: 4
---

# Visual Basic
*A visual guide to the basics*

## 1. Introduction
- **VB.NET (Visual Basic .NET)** is an object-oriented programming language developed by Microsoft.
- Mainly used for the creation of GUI apps but making text-based console apps is also possible but discouraged.

---

## 2. Syntax

### A. Comments
```vb
' this is a comment
' single line comments use a comma
' I know, this language is old af
```

### B. Variables & Data Types
*Only the useful ones*  
**Boolean**  
**Integer** also called **Int32**  
**Decimal**  
**Char**  
**String**  
**Object**  

### C. Operators
#### Arithmetic
```vb
[expression] + [expression]
[expression] - [expression]
[expression] * [expression]
[expression] / [expression] 'Float division
[expression] / [expression] 'Integer division
[expression] MOD [expression]
```

#### Comparison
```vb
[expression] = [expression] 'Equal, Fuck this one in particular
[expression] <> [expression] 'Not Equal
[expression] > [expression]
[expression] < [expression]
[expression] >= [expression]
[expression] <= [expression]
```

#### Logical
```vb
[booleanValue] And [booleanValue] 
[booleanValue] Or [booleanValue] 
[booleanValue] Xor [booleanValue]
[booleanValue] >= [booleanValue]
[booleanValue] <=> [booleanValue]
[booleanValue] AndAlso [booleanValue] 'TODO: Figure this out
[booleanValue] OrElse [booleanValue] 'TODO: Figure this out
Not [booleanValue]
[booleanValue] IsFalse
[booleanValue] IsTrue
```

#### Assignment
```vb
[variableName] = [value]
[variableName] += [value] 'Other basic operators apply
```

### D. Snippets
#### Declaring Variables
```vb
Dim [variableName] As [VariableType]
Dim num As Integer
```
```vb
Dim [variableName] As [VariableType] = [value]
Dim num As Integer = 6
```
#### Conditionals
```vb
If [condition] Then
    [statements]
Else 'Optional
    [statements]
End If
```
```vb
If([condition], [valueIfTrue], [valueIfFalse]) 'Ternary If
If(num=3, 5, 0)
```
#### Loops
```vb
For [variableName] As Integer = [initialValue] To [endValue]
    [statements]
    Continue For ' Optional, continue to next iter
    [statements]
    Exit For ' Optional, breaks loop
    [statements]
Next
```
```vb
While [condition]
    [statements]
    Continue While ' Optional, continue to next iter
    [statements]
    Exit While ' Optional, breaks loop
    [statements]
End While
```

#### Type Casting
```vb
    Convert.ToInt32([expression])
```

#### Functions
```vb
Function
    Return [expression]
End Function
```

#### Procedures
- A function that returns nothing  
- Useful for manipulating objects (i.e. clear UI or load from DB)  
```vb
Sub
    Return [expression]
End Sub
```

#### Exception Handling
```vb
Try
    [statements]
Catch [variableName] As Exception
    [statements]
End Try
```
```vb
Throw New Exception
```

## 3. Database Manipulation
- example
- under construction
```vb
Dim connectionString = [connectionString]
Using con As New SqlConnection(connectionString)
    con.Open()
    Dim query As String = "INSERT INTO players (id, name) VALUES (@id, @name)"
    Using cmd As New SqlCommand(query, con)
        cmd.Parameters.AddWithValue("@id", 3)
        cmd.Parameters.AddWithValue("@name", "john")
        cmd.ExecuteNonQuery() 
    End Using
End Using
```

### SqlCommand methods
**cmd.Parameters.AddWithValue([stringParameter], [value])**  
- for adding values to parameters  
**cmd.ExecuteNonQuery()**  
- for procedures that doesn't return data (i.e. INSERT)  
**cmd.ExecuteQuery()**  
**cmd.ExecuteScalar()**  
- if returning one row and one column  

## Still Under Construction