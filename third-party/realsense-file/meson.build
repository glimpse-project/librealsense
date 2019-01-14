src = [
    'lz4/lz4.c',

    'rosbag/roslz4/src/xxhash.c',
    'rosbag/roslz4/src/lz4s.c',

    'rosbag/console_bridge/src/console.cpp',

    'rosbag/rostime/src/duration.cpp',
    'rosbag/rostime/src/rate.cpp',
    'rosbag/rostime/src/time.cpp',

    'rosbag/cpp_common/src/header.cpp',
    'rosbag/cpp_common/src/debug.cpp',

    'rosbag/rosbag_storage/src/message_instance.cpp',
    'rosbag/rosbag_storage/src/query.cpp',
    'rosbag/rosbag_storage/src/bag.cpp',
    'rosbag/rosbag_storage/src/lz4_stream.cpp',
    'rosbag/rosbag_storage/src/chunked_file.cpp',
    'rosbag/rosbag_storage/src/view.cpp',
    'rosbag/rosbag_storage/src/buffer.cpp',
    'rosbag/rosbag_storage/src/stream.cpp',
    'rosbag/rosbag_storage/src/uncompressed_stream.cpp',
    'rosbag/rosbag_storage/src/bag_player.cpp',

    'rosbag/roscpp_serialization/src/serialization.cpp',
]

rs_file_inc = include_directories(
    'lz4',
    'boost',
    'rosbag/rosbag_storage/include',
    'rosbag/console_bridge/include',
    'rosbag/rostime/include',
    'rosbag/cpp_common/include',
    'rosbag/rosbag_storage/include',
    'rosbag/roscpp_traits/include',
    'rosbag/roslz4/include',
    'rosbag/roscpp_serialization/include',
    'rosbag/msgs'
)

rs_file_lib = static_library('realsense-file',
                             sources: src,
                             cpp_args: ['-DLZ4_DISABLE_DEPRECATE_WARNINGS', '-std=c++14'],
                             c_args: ['-std=c11'],
                             include_directories: [rs_file_inc],
                             dependencies: [])
rs_file_dep = declare_dependency(link_with: rs_file_lib,
                                 include_directories: [rs_file_inc])

