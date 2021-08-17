# GitVersionPackBug

[GitVersion.MsBuild] pack bug.  Basically including GitVersion.MsBuild when IsPackable=false, then calling `dotnet pack` on the project makes it fail to build.

## What it does

`dotnet pack` fails because GitVersion does not generate the `GitVersionInformation.g.cs` file:

```
C:\Users\cdonnelly\.nuget\packages\gitversion.msbuild\5.6.11\tools\GitVersion.MsBuild.targets(110,9): error : DirectoryNotFoundException: Could not find a part of the path 'D:\temp\marklar\obj\Debug\GitVersionInformation.g.cs'. [D:\temp\marklar\marklar.csproj]
```



[GitVersion.MsBuild]: https://www.nuget.org/packages/GitVersion.MsBuild/5.6.11
