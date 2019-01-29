
uv_src = [
    'ctrl.cpp',
    'ctrl-gen.cpp',
    'device.cpp',
    'diag.cpp',
    'frame.cpp',
    'init.cpp',
    'misc.cpp',
    'stream.cpp',
    'libuvc.cpp',
]

defines = [
    '-DUSE_SYSTEM_LIBUSB=1',
    '-DRS2_USE_LIBUVC_BACKEND',
]

public_inc = include_directories('.')

libusb_dep = dependency('libusb-1.0', required: true)

uvc_lib = static_library('uv',
                         sources: uv_src,
                         cpp_args: defines + ['-std=c++11'],
                         include_directories: [public_inc, src_inc],
                         dependencies: [libusb_dep])
uvc_dep = declare_dependency(link_with: uvc_lib,
                             include_directories: [public_inc])

