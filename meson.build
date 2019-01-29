project('realsense', ['c', 'cpp'],
        version: '2.17.1',
        license: 'Apache 2.0')

cc = meson.get_compiler('cpp')
compiler_id = cc.get_id()

math_dep = cc.find_library('m', required: false)
rt_dep = cc.find_library('rt', required: false)
threads_dep = dependency('threads')
glfw_dep = dependency('glfw3', fallback: [ 'glfw', 'glfw_dep' ], required: false)

rs_public_inc_dir = include_directories('include')

tp_inc_dir = include_directories('third-party')
subdir('third-party/sqlite')
subdir('third-party/realsense-file')
subdir('third-party/imgui')
subdir('src')

if glfw_dep.found()
    subdir('tools/realsense-viewer')
endif


