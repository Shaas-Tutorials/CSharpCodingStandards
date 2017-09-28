# Logility C# Coding Standards

## References

We generally want to follow the guidelines provided here:

* https://docs.microsoft.com/en-us/dotnet/standard/design-guidelines/

The standards specified below summarize the detailed Microsoft design guidelines. Where there are discrepancies, our guidelines take priority.

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
1. Do not use underscores, hyphens, or other non-alphanumeric characters, especially to separate words. Prefer `TextAlginment` rather than `text-alginment`.
1. Do not use Hungarian notation or its variants.
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


