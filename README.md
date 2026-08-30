[![](https://img.shields.io/nuget/v/soenneker.simpleicons.icons.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.simpleicons.icons/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.simpleicons.icons/build-and-test.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.simpleicons.icons/actions/workflows/build-and-test.yml)
[![](https://img.shields.io/nuget/dt/soenneker.simpleicons.icons.svg?style=for-the-badge)](https://www.nuget.org/packages/soenneker.simpleicons.icons/)
[![](https://img.shields.io/github/actions/workflow/status/soenneker/soenneker.simpleicons.icons/codeql.yml?style=for-the-badge)](https://github.com/soenneker/soenneker.simpleicons.icons/actions/workflows/codeql.yml)

# Soenneker.SimpleIcons.Icons

The Simple Icons SVG catalog packaged as content files for .NET applications.

## Installation

```bash
dotnet add package Soenneker.SimpleIcons.Icons
```

## Reading an icon

Package assets are copied beneath `Resources/SimpleIcons` in the consuming application's output directory. Filenames use the lowercase Simple Icons slug.

```csharp
string path = Path.Combine(
    AppContext.BaseDirectory,
    "Resources",
    "SimpleIcons",
    "github.svg");

string svg = await File.ReadAllTextAsync(path, cancellationToken);
```

The files contain complete SVG elements, including their accessible `<title>` and path data. They do not contain a fill color, so set color through CSS or by adding an appropriate SVG attribute when rendering.

## Web applications

The package copies files to build output, not directly into `wwwroot`. To expose an icon publicly, read and render it from the application or copy the required assets into your static-file directory as part of the consuming project. Avoid serving arbitrary user-provided filenames; map known icon names to known slugs instead.

This package contains assets only. Use `Soenneker.SimpleIcons.Enums.Icons` when code needs a generated enum of available icon names.
