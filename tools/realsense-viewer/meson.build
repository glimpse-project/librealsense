src = [
    'realsense-viewer.cpp',
    '../../common/rendering.h',
    '../../common/model-views.h',
    '../../common/model-views.cpp',
    '../../common/ux-window.h',
    '../../common/ux-window.cpp',
    '../../common/ux-alignment.cpp',
    '../../common/ux-alignment.h',

]

defines = [
    '-DGL_SILENCE_DEPRECATION',
    '-DNOC_FILE_DIALOG_OSX'
]

link_args = []
if host_machine.system() == 'darwin'
link_args += [
#    '-framework', 'Foundation',
    '-framework', 'OpenGL',
#    '-framework', 'CoreGraphics',
#    '-framework', 'QuartzCore',
#'-framework', 'UIKit',
]
endif
inc = include_directories('../../common')
executable('realsense-viewer', src,
           cpp_args: defines + ['-std=c++11'],
           link_args : link_args,
           include_directories: [tp_inc_dir, inc],
           dependencies: [rs_dep, imgui_dep, glfw_dep])
