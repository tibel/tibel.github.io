---
layout: post
title: Using value converters by convention
---

Cum sociis natoque penatibus et magnis dis `code element` montes, nascetur ridiculus mus. Rouge

``` csharp
/// <summary>
/// Denotes an object that has no fixed value, but can resolve it's value on runtime.
/// </summary>
public interface ISpecialValue
{
	/// <summary>
	/// Resolves the value of this instance.
	/// </summary>
	/// <param name="context">The context.</param>
	/// <returns>The resolved value.</returns>
	object Resolve(CoroutineExecutionContext context);
}
```

Etiam porta sem malesuada magna mollis euismod. Cras mattis consectetur purus sit amet fermentum. Aenean lacinia bibendum nulla sed consectetur.
