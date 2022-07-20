# Files to look at
1. Program.cs line 4 `.AddRazorRuntimeCompilation()`
2. GlobalUsings.cs contains a global using for `System.Diagnostics`
3. Index.cshtml contains a line of code that requires `System.Diagnostics` `Debugger.IsAttached`

Running the project currently results in this error:
```
An error occurred during the compilation of a resource required to process this request. Please review the following specific error details and modify your source code appropriately.
C:\Git\GitHub\AddRazorRuntimeCompilation-Global-Usings-Example\AddRazorRuntimeCompilationGlobalUsingsExample\AddRazorRuntimeCompilationGlobalUsingsExample\Views\Home\Index.cshtml

The name 'Debugger' does not exist in the current context
+
    @if (Debugger.IsAttached)
```

If you add the using back to Index.cshtml it will work. Or if you remove `.AddRazorRuntimeCompilation()` from Program.cs
The global using is not picked up when the page is compiled at runtime.