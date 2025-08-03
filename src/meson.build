# if frida_core_dep.type_name() == 'internal'
#   frida_core_subprj = subproject('frida-core')
#   frida_gir = frida_core_subprj.get_variable('core_public_gir')
#   glib_gir = frida_core_subprj.get_variable('glib_gir')
#   gobject_gir = frida_core_subprj.get_variable('gobject_gir')
#   gio_gir = frida_core_subprj.get_variable('gio_gir')
# else
#   girdir = frida_core_dep.get_variable('frida_girdir')
#   frida_gir = girdir / 'Frida-1.0.gir'
#   glib_gir = girdir / 'GLib-2.0.gir'
#   gobject_gir = girdir / 'GObject-2.0.gir'
#   gio_gir = girdir / 'Gio-2.0.gir'
# endif

girdir = meson.current_build_dir() / '..' / 'subprojects' / 'frida-core' / 'src' / 'api'
frida_gir = meson.current_build_dir() / '..' / 'subprojects' / 'frida-core' / 'src' / 'api' / 'Frida-1.0.gir'

# Generate bindings
custom_target('binding-code',
  output: ['testasdasd'],
  input: [
    girdir,
    frida_gir
  ],
  command: [
    girtool,
    'generate',
    '--search-path-macos', '@INPUT0@',
    '@INPUT1@'
  ],
  depends: [girtool]
)
