---
layout: default
title: Result and Result`T types in C#
parent: Functional Programming in C#
grand_parent: Functional Programming
nav_order: 1
has_children: false
permalink: functional-programming/csharp/result-and-result`1-types
---

## Result and Result`T types in C#

```csharp
using System;

public class Result
{
    public bool IsSuccess { get; }

    public string FailMessage { get; }

    protected Result(bool isSuccess, string failMessage)
    {
        if (isSuccess && failMessage != null || !isSuccess && failMessage == null)
        {
            var message = $"Can't initialize an instance of {nameof(Result)} type.";
            throw new InvalidOperationException(message);
        }

        IsSuccess = isSuccess;
        FailMessage = failMessage;
    }

    public static Result CreateFail(string failMessage)
    {
        return new Result(false, failMessage);
    }

    public static Result<T> CreateFail<T>(string failMessage)
    {
        return new Result<T>(default(T), false, failMessage);
    }

    public static Result CreateSuccess()
    {
        return new Result(true, null);
    }

    public static Result<T> CreateSuccess<T>(T value)
    {
        return new Result<T>(value, true, null);
    }
}

public class Result<T> : Result
{
    public T Value { get; }

    protected internal Result(T value, bool isSuccess, string failMessage) :
        base(isSuccess, failMessage)
    {
        Value = value;
    }
}
```

---
### Additional resources list

[Functional Programming in C#: How to write better C# code](https://learning.oreilly.com/library/view/functional-programming-in/9781617293955/)  
[Applying Functional Principles in C#](https://app.pluralsight.com/library/courses/csharp-applying-functional-principles/table-of-contents)    