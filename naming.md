# Naming

## Capitalization

Note that the design guidelines refer to "PascalCasing." This is also referred to as "TitleCasing," as distigusihed from "camcelCasing."

1. Use the table below as a guideline for when to use PascalCasing and when to use camcelCasing.

 Identifier | Casing
 ---------- | ------
 Namespace | Pascal 
 Type | Pascal
 Interface | Pascal
 Method | Pascal
 Property | Pascal
 Event | Pascal
 Field | Pascal
 Enum value | Pascal
 Parameter | Camel
 Local variable | Camel

2. Use all caps for acronyms of length 2 only.

 All-cap: IO, UI

 Not all-cap: Ok, No, Api, Web, Lom, Fif, Etc

3. Never use two identifiers that differ only in case. Assume case insensitivity, but use proper casing. For example, do not have two public methods named `GetProperty` and `getProperty`.

## Word Choice

1. Choose names that read naturally in English.
1. Do not use underscores, hyphens, or other non-alphanumeric characters, especially to separate words. Prefer `TextAlignment` rather than `text-alignment`.
1. Do not use Hungarian notation or its variants.
1. Use semantically meaningful names rather than including a type in the name, except when the type is integral to the meaning of the method. For example, `GetLength` is preferred for the length of a string, whereas `GetInt32` can be used when fetching an integer type from a data reader.
1. Avoid using names that are keywords in C# or VB.Net.
1. Try to avoid using names that conflict with .NET public names, such as `Exception`

## Assemblies and Binaries

1. Assembly names should take the form `Voyager.Prod.Component`, where `Prod` is a product acronym, and `Component` is specific to the product. For example:
 - `Voyager.IO.Core`
 - `Voyager.DP.Fcp`
1. The component portion can have portions after it, separate by periods. For example:
 - `Voyager.Ito.Modules.Core`
1. DLL file names should be named the same as the assembly. For example:
 - `Voyager.IO.Core.dll`
1. EXE file names can be named shorter if they are intended to be run from a command line. For example:
 - `ConfigLoader.exe` (assembly name is `Voyager.IO.Configuration.ConfigLoader`)
1. EXE file names that are not run from a command line or batch file should be named the same as the assembly. This includes executables that get launched from our code or via COM instantiation. For example:
 - `Voyager.Ito.Platform.ProcessorHost.exe`

## Namespaces

1. Namespaces should be of the form: `Logility.Voyager.Prod.Abc.Etc` where `Prod` is the product acronym, and `Abc.Etc` are specific to the product. For example:
 ````csharp
 namespace Logility.Voyager.IO.Core.Configuration { }
 namespace Logility.Voyager.Core.Security { }
 ````
1. Do not use the same name for a namespace and a type within that namespace.
1. Within an assembly, try to keep all namespaces as refinements on the assembly name (with `Logility` in front). For example, the assembly `Voyager.IO.Core` could contain the `Logility.Voyager.IO.Core.Configuration` namespace but shouldn't contain a `Logility.Voyager.Core.Security` namespace.

## Classes, Structs, and Interfaces

1. Name classes and structs with nouns or noun phrases.
1. Name interfaces with adjective phrases when possible, although noun or noun phrases are acceptable.
1. Prefix interfaces with the letter I and use PascalCase for the portion after the I. For example, `IPascalCaseable`

See https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/names-of-classes-structs-and-interfaces for further details, especially on naming common types (attributes, exceptions), generic type parameters, and enumerations.

## Type Members

### Methods

1. As methods are actions, use verb or verb phrases for methods when possible, in order to help distinguish them from properties.

Remember also the other guidelines about keeping names naturally readable, so prefer `ValidatePassword` over `PasswordValidate`.

### Properties

1. Use noun or noun phrases for properties.
1. For collections, use a plural phrase rather than appending the word List or Collection. For example, prefer `Locations` over `LocationList`.
1. Use affirmative phrasing for boolean properties. For example, prefer `CanRead` instead of `CannotRead` (which will just lead to confusion).

### Fields

Fields include public and protected fields that behave somewhat like properties (just with getter/setter implementations), as well as private fields, also known sometimes as class variables.

1. For public and protected fields, use the naming guidelines for Properties.
1. For private fields, use camelCasing with an underscore prefix. For example:
 ````csharp
 private int _locationId;
 ````
1. Private fields should have semantically meaningful names, just like all public/protected members.

## Parameters

1. Use descriptive parameter names. For example, prefer `index` over `i`. An exception is when the parameter name is redundant to the name of the method. For example, prefer `GetValueAtIndex(int i)` over `GetValueAtIndex(int index)`.
