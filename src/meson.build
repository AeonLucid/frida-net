fs = import('fs')

if frida_core_dep.type_name() == 'internal'
  frida_core_subprj = subproject('frida-core')
  frida_gir = frida_core_subprj.get_variable('core_public_gir')
  girdir = fs.parent(frida_gir)
else
  girdir = frida_core_dep.get_variable('frida_girdir')
  frida_gir = girdir / 'Frida-1.0.gir'
endif

# Generate bindings
generate_bindings = custom_target('generate-bindings',
  output: ['aaa'],
  command: [
    girtool,
    'generate',
    '--search-path-linux', girdir,
    '--search-path-macos', girdir,
    '--search-path-windows', girdir,
    '--output', meson.current_build_dir(),
    frida_gir
  ],
  build_by_default: true
)

# 