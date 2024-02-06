# "Flogger" is simple and fast logging library for Modern Fortran applications.
#  https://github.com/rbarrel/flogger
#  https://github.com/arifyunando/flogger
# 
#  MIT License
# 
#  Copyright (c) 2024 Nolan McMahon, RainBarrel Inc.
#  Copyright (c) 2023 Arif Y. Sunanhadikusuma
# 
#  Permission is hereby granted, free of charge, to any person obtaining a copy
#  of this software and associated documentation files (the "Software"), to deal
#  in the Software without restriction, including without limitation the rights
#  to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
#  copies of the Software, and to permit persons to whom the Software is
#  furnished to do so, subject to the following conditions:
# 
#  The above copyright notice and this permission notice shall be included in all
#  copies or substantial portions of the Software.
# 
#  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
#  IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
#  FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
#  AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
#  LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
#  OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
#  SOFTWARE.
#
project(
  'flogger',
  'fortran',
  version: '0.0.0',
  default_options: ['werror=true'],
)

install = not (meson.is_subproject() and get_option('default_library') == 'static')

srcs = []
subdir('src')

flogger_lib = library(
  meson.project_name(),
  sources: srcs,
  install: install,
)

pkg = import('pkgconfig')
pkg.generate(
  flogger_lib,
  description: 'Flogger is a simple and fast logging library for Modern Fortran applications.',
)

# Export flogger as a Dependency for Other Projects
flogger_inc = flogger_lib.private_dir_include()
flogger_dep = declare_dependency(
  link_with: flogger_lib,
  include_directories: flogger_inc,
)
