project('proxy-libintl', 'c',
  version : '1',
  meson_version : '>= 0.27.0',
  default_options : [ 'warning_level=1',
                      'c_std=gnu99',
                      'buildtype=debugoptimized' ])

install_headers('libintl.h')

intl_srcs = ['libintl.c']

intl_static_lib = static_library('intl',
  intl_srcs,
  c_args: ['-DSTUB_ONLY'],
  install : true)

intl_lib = library('intl',
  intl_srcs,
  link_with: intl_static_lib,
  install : true)

intl_dep = declare_dependency(link_with : intl_lib,
  include_directories : include_directories('.'))
