sqlite_src = [
    'sqlite3.c'
]

sqlite_inc = include_directories('.')

sqlite_lib = static_library('sqlite',
                            sources: sqlite_src,
                            dependencies: [threads_dep])
sqlite_dep = declare_dependency(link_with: sqlite_lib,
                                include_directories: [sqlite_inc])

