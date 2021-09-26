project('ocr', 'c', 'cpp',
  version : '1',
  default_options : ['warning_level=3'])

add_project_arguments('-ffast-math', language : 'c')

sources = [
     'src/ocr.c'
]

vapoursynth_dep = dependency('vapoursynth', version: '>=55').partial_dependency(compile_args : true, includes : true)
libtesseract_dep = dependency('tesseract')

deps = [vapoursynth_dep, libtesseract_dep]

shared_module('ocr', sources,
  dependencies : deps,
  install : true,
  install_dir : join_paths(vapoursynth_dep.get_pkgconfig_variable('libdir'), 'vapoursynth'),
  gnu_symbol_visibility : 'hidden'
)
