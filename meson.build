project('frida-net', 'c',
  version: run_command(find_program('python3'), files('tools' / 'detect-version.py'),
    capture: true,
    check: true).stdout().strip(),
  meson_version: '>=1.1.0',
  default_options: [],
)

frida_core_dep = dependency('frida-core-1.0', default_options: [
  'frida_version=' + meson.project_version()
])

girtool = custom_target(
  'build-gir-tool',
  output: 'GirTool',
  command: [
    'dotnet',
    'publish',
    '-o', 'girtool-build',
    '-c', 'Release',
    '-p:PublishSingleFile=true',
    meson.current_source_dir() / 'gir.core' / 'src' / 'Generation' / 'GirTool' / 'GirTool.csproj',
    '&&',
    'cp', 'girtool-build/GirTool', '@OUTPUT@'
  ],
  build_by_default: true
)

subdir('src')