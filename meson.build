project('frida-net', 'c',
  version: run_command(find_program('python3'), files('tools' / 'detect-version.py'),
    capture: true,
    check: true).stdout().strip(),
  meson_version: '>=1.4.0',
  default_options: [],
)

frida_core_dep = dependency('frida-core-1.0', default_options: [
  'frida_version=' + meson.project_version()
])

# Build girtool
host = host_machine
exe_suffix = host.system() == 'windows' ? '.exe' : ''

girtool = custom_target(
  'build-gir-tool',
  output: 'GirTool' + exe_suffix,
  command: [
    'dotnet',
    'publish',
    '-o', meson.current_build_dir(),
    '-c', 'Release',
    '-p:PublishSingleFile=true',
    meson.current_source_dir() / 'gir.core' / 'src' / 'Generation' / 'GirTool' / 'GirTool.csproj'
  ],
  build_by_default: true
)

subdir('src')