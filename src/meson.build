fs = import('fs')

if frida_core_dep.type_name() == 'internal'
  frida_core_subprj = subproject('frida-core')
  frida_gir = frida_core_subprj.get_variable('core_public_gir')
  girdir = fs.parent(frida_gir)
else
  girdir = frida_core_dep.get_variable('frida_girdir')
  frida_gir = girdir / 'Frida-1.0.gir'
endif

subdir('Frida.NET.Bindings')
subdir('Frida.NET')
