---
layout: post
title: Using value converters by convention
---

Cum sociis natoque penatibus et magnis dis `code element` montes, nascetur ridiculus mus.

``` csharp
var baseApplyValueConverter = ConventionManager.ApplyValueConverter;

ConventionManager.ApplyValueConverter = (binding, bindableProperty, property) =>
{
    baseApplyValueConverter(binding, bindableProperty, property);

    if (bindableProperty == TextBlock.TextProperty && typeof(DateTime).IsAssignableFrom(property.PropertyType))
        binding.Converter = new RelativeDateTimeConverter();

    if (bindableProperty == TextBlock.TextProperty && typeof(DateTimeOffset).IsAssignableFrom(property.PropertyType))
        binding.Converter = new RelativeDateTimeConverter();
};
```

Etiam porta sem malesuada magna mollis euismod. Cras mattis consectetur purus sit amet fermentum. Aenean lacinia bibendum nulla sed consectetur.
