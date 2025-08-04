
fs = import('fs')

project_file = fs.copyfile('Frida.NET.csproj', 'Frida.NET.csproj')

custom_target(
  'build-library',
  input: project_file,
  output: 'Frida.NET.1.0.0.nupkg',
  command: [
    'dotnet',
    'pack',
    '-o', meson.current_build_dir(),
    '-c', 'Release',
    project_file
  ],
  build_by_default: true
)