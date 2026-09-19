# Blazorade Design Principles

Blazorade aims to make developing Blazor applications easier with Blazorade than without it. Blazor is a web UI framework that enables developers to build interactive applications with .NET. Blazor applications commonly integrate with client-side web libraries, which may involve varying amounts of JavaScript. These libraries may expose similar capabilities through very different programming models, requiring developers to adapt to each library's way of doing things.

The following principles describe how Blazorade libraries should reduce that friction and provide a familiar and intuitive programming model across the Blazorade family.

## Write No JavaScript

Blazorade libraries should take advantage of the fact that Blazor applications allow developers to write application behavior in .NET. They should make library features available through .NET APIs as the natural starting point for developers.

When an underlying web library exposes functionality through JavaScript, Blazorade should handle the JavaScript interoperability and expose the functionality through natural .NET APIs where practical.

Blazorade libraries should also provide access to the underlying JavaScript APIs when developers need capabilities or control beyond the .NET APIs.

## Follow Established .NET and Blazor Practices

Blazorade libraries should follow established best practices for .NET and Blazor in the functionality they provide. Developers should be able to use familiar patterns, APIs, and conventions when working with different Blazorade libraries, even when those libraries wrap underlying technologies that have different programming models.

Blazorade libraries should do the heavy lifting when adapting client-side libraries to an established .NET and Blazor programming model. They should absorb unnecessary differences between those technologies and expose their capabilities through idiomatic Blazor and .NET APIs. They should expose library-specific concepts and constraints when those concepts are meaningful to the library's use in Blazor.

## Support Blazor Hosting Models

Blazorade libraries should aim to support the main Blazor hosting models: Blazor Server, Blazor WebAssembly, and .NET MAUI Blazor Hybrid. APIs and components should be designed with the differences between these models in mind, allowing developers to use the same library across as many hosting models as practical.

Some components may depend on capabilities specific to a particular hosting model. In those cases, the component should clearly communicate its supported model and provide a focused experience for it.

## Minimal by Default

Blazorade components and functionality should have sensible defaults. A component should produce meaningful HTML markup and useful behavior with no parameters or with only minimal configuration.

Defaults should provide a useful starting point alongside deep customization. Developers should be able to override or replace default functionality and take control of the produced HTML markup when their application requires it.

Blazorade components should encapsulate boilerplate markup, configuration, and integration details behind understandable components and APIs, while still allowing developers to provide the content and customization they need. Developers should be able to accomplish common tasks with concise markup.

## Rely on IntelliSense and Auto-Complete

Blazorade APIs should make the capabilities of a library discoverable through the tools developers already use. Parameters, methods, enum values, and other public members should have clear names and meaningful documentation.

Where a library wraps conventions based on CSS classes, attributes, or nested elements, it should expose the most useful choices through discoverable parameters, enums, constants, templates, or other appropriate .NET types.

Names should generally be more descriptive than the abbreviated names sometimes used by the underlying HTML, CSS, or JavaScript library. The goal is to make authoring Blazorade components intuitive and keep routine usage discoverable through IntelliSense and auto-complete.

