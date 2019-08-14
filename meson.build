project('proxy-libintl', 'c',
  version : '1',
  meson_version : '>= 0.27.0',
  default_options : [ 'warning_level=1',
                      'c_std=gnu99',
                      'buildtype=debugoptimized' ])

install_headers('libintl.h')

intl_shr = shared_library('intl',
  'libintl.c',
  c_args: ['-DSTUB_ONLY'],
  install : true)

intl_sta = static_library ('intl',
  'libintl.c',
  c_args: ['-DSTUB_ONLY', '-DG_INTL_STATIC_COMPILATION'],
  install : true)

compile_args_export = []
if get_option('default_library') == 'static'
  intl_lib = intl_sta
  compile_args_export += '-DG_INTL_STATIC_COMPILATION'
else
  intl_lib = intl_shr
endif

intl_dep = declare_dependency(link_with : intl_lib,
  compile_args: compile_args_export,
  include_directories : include_directories('.'))
