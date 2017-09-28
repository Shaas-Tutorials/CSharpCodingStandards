# Layout

## Folder Layout

### Projects and Solutions

1. Keep one project (assembly) per folder. Do not include two projects in the same folder.
  - Exception would be the case where you have separate projects of the same assembly to target different versions of .NET.
1. Some products prefer one project per solution. In this case, the solution file should be in the same folder as the project file.
1. Project file name should match the assembly name.

### Folders and Files

1. Consider having subfolders follow the name of the portions of the namespaces that come after the assembly name portion.
  - For example, suppose an assembly named `Voyager.YP` with a default (base) namespace of `Logility.Voyager.YP` has classes in two separate namespaces:
    ````csharp
    namespace Logility.Voyager.YP.Models { public class LocationModel { }}
    namespace Logility.Voyager.YP.Controllers { public class LocationController { }}
    ````
    Then, the folder containing the `Voyager.YP` project file would have two subfolders:
    - Models
      - LocationModel.cs
    - Controllers
      - LocationController.cs

