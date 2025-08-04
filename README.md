# frida-net - WIP

## TODO

- [x] Build gir.core with meson
  - clone
  - cd gir.core/scripts
  - dotnet fsi GenerateLibs.fsx
  - cd ../src
  - dotnet build GirCore.Libs.slnf
- [x] Build gir.core/GirTool with meson
- [x] Properly call GirTool to generate sources
- [ ] Make everything internal of generated bindings except enums and delegates
- [ ] On windows, build frida-core with `windows-x86_64-md`
