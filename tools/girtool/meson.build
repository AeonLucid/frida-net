host = host_machine
exe_suffix = host.system() == 'windows' ? '.exe' : ''

girinit = custom_target('initialize-gir-core',
  output: 'girinit.stamp',
  input: [
    files('initialize-gir-core.py')
  ],
  command: [
    'python',
    files('initialize-gir-core.py'),
    '--gir-scripts', meson.source_root() / 'gir.core' / 'scripts',
    '--gir-src', meson.source_root() / 'gir.core' / 'src',
    '--dummy-output-file', '@OUTPUT@',
  ]
)

girtool = custom_target('build-gir-tool',
  output: 'GirTool' + exe_suffix,
  depends: [girinit],
  command: [
    'dotnet',
    'publish',
    '-o', meson.current_build_dir(),
    '-c', 'Release',
    '-p:PublishSingleFile=true',
    meson.source_root() / 'gir.core' / 'src' / 'Generation' / 'GirTool' / 'GirTool.csproj'
  ],
  build_by_default: true
)