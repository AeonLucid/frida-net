# frida-net - WIP

## TODO

- [ ] Build gir.core with meson
  - clone
  - cd gir.core/scripts
  - dotnet fsi GenerateLibs.fsx
  - cd ../src
  - dotnet build GirCore.Libs.slnf
- [ ] Build gir.core/GirTool with meson
- [ ] Properly call GirTool to generate sources
- [ ] On windows, build frida-core with `windows-x86_64-md`
