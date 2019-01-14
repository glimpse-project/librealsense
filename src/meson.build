
#uvc_dep = dependency('libuvc', required: false)
#if not uvc_dep.found()
subdir('libuvc')
#endif

src = [
    'linux/backend-v4l2.cpp',
    'linux/backend-hid.cpp',

    'ds5/ds5-options.cpp',
    'ds5/ds5-timestamp.cpp',
    'ds5/ds5-private.cpp',
    'ds5/ds5-motion.cpp',
    'ds5/ds5-rolling-shutter.cpp',
    'ds5/ds5-device.cpp',
    'ds5/ds5-color.cpp',
    'ds5/ds5-active.cpp',
    'ds5/ds5-factory.cpp',
    'ds5/advanced_mode/rs_advanced_mode.cpp',
    'ds5/advanced_mode/presets.cpp',
    'ds5/advanced_mode/advanced_mode.cpp',

    'ivcam/ivcam-private.cpp',
    'ivcam/sr300.cpp',

    'l500/l500.cpp',
    'l500/l500-private.cpp',

    'media/record/record_device.cpp',
    'media/record/record_sensor.cpp',
    'media/playback/playback_device.cpp',
    'media/playback/playback_sensor.cpp',

    'mock/sql.cpp',
    'mock/recorder.cpp',

    'proc/sse/sse-align.cpp',
    'proc/processing-blocks-factory.cpp',
    'proc/align.cpp',
    'proc/colorizer.cpp',
    'proc/pointcloud.cpp',
    'proc/occlusion-filter.cpp',
    'proc/synthetic-stream.cpp',
    'proc/syncer-processing-block.cpp',
    'proc/decimation-filter.cpp',
    'proc/spatial-filter.cpp',
    'proc/temporal-filter.cpp',
    'proc/hole-filling-filter.cpp',
    'proc/disparity-transform.cpp',
    'proc/rates_printer.cpp',

    'pipeline/pipeline.cpp',
    'pipeline/config.cpp',
    'pipeline/profile.cpp',
    'pipeline/aggregator.cpp',

    'environment.cpp',
    'device_hub.cpp',
    'archive.cpp',
    'context.cpp',
    'device.cpp',
    'sensor.cpp',
    'algo.cpp',
    'sync.cpp',
    'stream.cpp',
    'option.cpp',
    'error-handling.cpp',
    'hw-monitor.cpp',
    'image.cpp',
    'image_avx.cpp',
    'log.cpp',
    'rs.cpp',
    'types.cpp',
    'backend.cpp',
    'verify.c',
    'software-device.cpp',
    'source.cpp',
]

if host_machine.system() == 'windows'
src += [
    'win/win-helpers.cpp',
    'win/win-uvc.cpp',
    'win/win-usb.cpp',
    'win/win-hid.cpp',
    'win/win-backend.cpp',
]
endif

defines = [
    '-DUSE_SYSTEM_LIBUSB=1',
    '-DRS2_USE_LIBUVC_BACKEND=1'
]

libusb_dep = dependency('libusb-1.0', required: true)

rs_lib = library('realsense',
                  sources: src,
                  cpp_args: defines + ['-DLZ4_DISABLE_DEPRECATE_WARNINGS', '-std=c++11'],
                  include_directories: [rs_public_inc_dir],
                  dependencies: [uvc_dep, rs_file_dep, sqlite_dep])
rs_dep = declare_dependency(link_with: rs_lib,
                             include_directories: [rs_public_inc_dir])

