imgui_src = [
    'imgui.cpp',
    'imgui_draw.cpp',
    'imgui_impl_glfw.cpp',
    'imgui-fonts-karla.hpp',
    'imgui-fonts-fontawesome.hpp'
]

imgui_inc = include_directories('.')

imgui_lib = static_library('imgui',
                            sources: imgui_src,
                            cpp_args: ['-std=c++11'],
                            dependencies: [])
imgui_dep = declare_dependency(link_with: imgui_lib,
                               include_directories: [imgui_inc])

