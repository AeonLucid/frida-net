fs = import('fs')

project_file = fs.copyfile('Frida.NET.csproj', 'Frida.NET.csproj')

build_library = custom_target(
  'build-library',
  input: project_file,
  output: 'Frida.NET.1.0.0.nupkg',
  depends: [build_library_bindings],
  command: [
    'dotnet',
    'pack',
    '-o', meson.current_build_dir(),
    '-c', 'Release',
    project_file
  ],
  build_by_default: true
)