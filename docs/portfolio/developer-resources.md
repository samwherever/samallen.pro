---
title: Developer Resources

---

!!! note
    These were written to help standardize how developers were naming and structuring various aspects of their development work.


#### Coding Standards

This is a guide to Sertifi coding standards. Standards ensure the code will look and feel similar throughout the codebase, which enables easier navigation and debugging.

**Variables**

| Type | Format | Example |
|------|--------|---------|
|Protected and private variables|camelCase|`private int _myInt;`|
| Class names | PascalCase | `public class MyClass {};` |
| Public properties | PascalCase | `public int MyInt;` |
| Public properties | PascalCase | `public int MyInt;` |
| Interfaces | Capitalized Case. Interface names must always start with a capital "I" (as in indigo). | `IMyInterface`|
| Constants | All capital letters, separated by underscores. Never use spaces. | `NUMBER_OF_CATS`|

!!! tip
    Avoid using type identification in variable and function identifiers, like `string stringName`, `bool bResult`, and so on.



**Lambda Expressions**

All lambda methods should start on a new line after the first line of the method.

```csharp
myList.Where(x => x.SomeProp = 1);
```

```csharp
myList.Where(x => x.SomeProp = 1)
      .Select(s => s.SomeProp2);
```

When using `.join`, use a complete word for the lambda variable name.

**Project Names**

Project names should start with Sertifi, e.g. Sertifi.*nameofProject*. When necessary, add the layer to the name after Sertifi, e.g. Sertifi.*BL.Core* for core business logic.

Unit test projects should use the format of Sertifi.*nameOfProjectBeingTest*.Test
