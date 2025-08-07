if frida_core_dep.type_name() == 'internal'
  frida_core_subprj = subproject('frida-core')
  frida_core_lib = frida_core_subprj.get_variable('core_public_lib')
else
  frida_core_lib = frida_core_dep
endif

host_system = host_machine.system()

if host_system == 'windows'
  vs_module_defs = 'Frida.def'
else
  vs_module_defs = ''
endif

wrapper_sources = files('frida-wrapper.c')

frida_dll = shared_library(
  'Frida',
  wrapper_sources,
  dependencies: [ frida_core_dep ],
  vs_module_defs: vs_module_defs
)