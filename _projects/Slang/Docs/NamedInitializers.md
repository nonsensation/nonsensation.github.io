---
draft: true

layout: page
toc: false

categories: ["Slang"]
tags: ["Programming Language Design"]

title: "Slang - Named Initializers"
---


# Named Initializers


- if in order, only for different types, fieldname is optional
- if one fieldname is given, all need a fieldname
- out of order only with fieldname
- nested fieldnames
- array with either .0 notation or .[], can also be nested

## Named Object Initializers

```
type Person : struct {
    FirstName : string
    LastName : string
    Age : integer
}

Jack : Person = { "Jack" , "Reacher" , 22 }

Jack : Person = {
    .LastName = "Reacher"
    .FirstName = "Jack"
    .Age = 22
}
```

```
type Person : struct {
    type Name : struct {
        FirstName : string
        LastName : string
        Age : integer
    }
    Age : integer
    Name : Name
}

Sara : Person = {
    .Name.LastName = "Reacher"
    .Name.FirstName = "Sara"
    .Age = 22
}
Jack : Person = {
    .Name = {
        .LastName = "Reacher"
        .FirstName = "Jack"
    }
    .Age = 22
}
```

## Named Array Initializers

```
array : int[] = {
    .0 = 0
    .[ 1 ] = 1
    .[ -1 ] = 8
    .[ 2..4 ] = 0
}

matrix : int[][] = {
    .[ 0 ][ 0 ] = 1
}
```



```
Jack : Person = {
    .LastName = "Reacher"
    .FirstName = "Jack"
    .Age = 22
}
```
{: .good}



```
Jack : Person = {
    .LastName = "Reacher"
    .FirstName = "Jack"
    22 // fieldname not specified
}
```
{: .bad txt="fieldname not specified"}



```

```
{: .good}



```

```
{: .bad}

---

{:.info}
Similar to named initializers are [Named Arguments](NamedArguments)
