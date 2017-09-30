# Layout

## Folder Layout

### Projects and Solutions

1. Keep one project (assembly) per folder. Do not include two projects in the same folder.
  - Exception would be the case where you have separate projects of the same assembly to target different versions of .NET.
2. Some products prefer one project per solution. In this case, the solution file should be in the same folder as the project file.
3. Project file name should match the assembly name.

### Folders and Files

1. Consider having subfolders follow the name of the portions of the namespaces that come after the assembly name portion.
  - For example, suppose an assembly named `Voyager.YP` with a default (base) namespace of `Logility.Voyager.YP` has classes in two separate namespaces:
    ````csharp
    namespace Logility.Voyager.YP.Models { public class LocationModel { } }
    namespace Logility.Voyager.YP.Controllers { public class LocationController { } }
    ````
    Then, the folder containing the `Voyager.YP` project file would have two subfolders:
    - Models
      - LocationModel.cs
    - Controllers
      - LocationController.cs
2. Do have one type per file.
3. File names should match as closely as possible the type defined in the file.
4. Consider only sparing use of partial type definitions (where a single type is defined in multiple files). This is often an indication that a type should be refactored into multiple types.

## Class and Structure Layout

The use of "class" below refers to both class and structures, when appropriate for both.

1. Consider putting constructors first in a class definition.
2. Group type members (methods, properties, fields, events, etc.) together by functional relationship. This is generally preferred over putting all properties together, all methods together, all private members together, etc.
3. If there is a property (getter/setter) that uses a private field, include the private field immediately after the property. For example:
  ```csharp
  public int LocationId {
      get {
          return _locationId;
      }
      set {
          if(value<0) throw new ArgumentException();
          _locationId = value;
      }
  }
  private int _locationId = 0;
  ```
4. Use `#region`/`#endregion` blocks sparingly to group together like members (e.g., a set of like-named overloaded methods).
5. Write one declaration per line.
6. Add a blank line between type definitions.

## Commenting

1. Place comments on separate lines. Use comments at end of lines of code sparingly.
2. Consider writing comments in sentence or sentence fragment form; start with upper-case character, end with period.
3. Include a space after the comment delimiter and before comment text. For example,
  ```csharp
  // Calculates cumulative normal distribution function.
  ```
4. Do not create ASCII boxes of asterisks or other characters around comments.

## Code Styling and White Space

Preferred settings in the Visual Studio 2017 Text Editor (C#) settings dialog.

### Tabs

* Indenting = Smart
* Tab size = 4
* Indent size = 4
* Keep tabs = checked

### Code Style

#### General

* `this.` preferences
  * All should be "Do not prefer this." with severity "None"
* predefined type preferences
  * All should be "Prefer predefined type" with severity "None"
* `var` preferences
  * All should be "Prefer explicit type" with severity "None"
* Code block preferences
  * Prefer braces = "Yes" with Severity "Suggestion"
* Expression preferences
  * Prefer object initializer = "Yes" with Severity "Suggestion"
  * Prefer collection initializer = "Yes" with Severity "Suggestion"
  * Prefer pattern matching over `is` with `cast` check = "Yes" with Severity "Suggestion"
  * Prefer pattern matching over `as` with `null` check = "Yes" with Severity "Suggestion"
  * Prefer explicit tuple name = "Yes" with Severity "Suggestion"
  * Prefer simple `default` expression = "Yes" with Severity "Suggestion"
  * **Use expression body for methods = "When on single line" with Severity "None"**
  * Use expression body for constructors = "Never" with Severity "None"
  * Use expression body for operators = "Never" with Severity "None"
  * Use expression body for properties = "When possible" with Severity "None"
  * Use expression body for indexers = "When possible" with Severity "None"
  * Use expression body for accessors = "When possible" with Severity "None"
* Variable preferences
  * Prefer inlined variable declaration = "Yes" with Severity "Suggestion"
* `null` checking
  * Prefer throw-expression = "Yes" with Severity "Suggestion"
  * Prefer condition delegate call = "Yes" with Severity "Suggestion"
  * Prefer coalesce expression = "Yes" with Severity "Suggestion"
  * Prefer null propagation = "Yes" with Severity "Suggestion"

#### Formatting - Indentation

* Indent block contents = checked
* Indent open and close braces = unchecked
* Indent case contents = checked
* Indent case labels = checked
* Label indentation = "Indent labels normally"

#### Formatting - New Lines

* New line options for braces
  * All should be unchecked
* New line options for keywords
  * All should be checked
* New line options for expressions
  * All should be checked

#### Formatting - Spacing

* Set spacing for method declarations
  * All should be unchecked
* Set spacing for method calls
  * All should be unchecked
* Set other spacing options
  * Insert space after keywords in control flow statements = checked
  * The rest should be unchecked
* Set spacing for brackets
  * All should be unchecked
* Set spacing for delimiters
  * Insert space after colon for base or interface in type declaration = checked
  * Insert space after comma = checked
  * Insert space after dot = unchecked
  * Insert space after semicolon in `for` statement = checked
  * Insert space before colon for base or interface in type declaration = checked
  * Insert space before comma = unchecked
  * Insert space before dot = unchecked
  * Insert space before semicolon in `for` statement = unchecked
* Set spacing for operators = Insert space before and after binary operators

#### Formatting - Wrapping

* Leave block on single line = checked
* Leave statements and member declarations on the same line = checked



