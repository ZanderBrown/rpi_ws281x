project('rpi-ws281x', 'c', version: '1.1.0')

sources = [
    'mailbox.c',
    'ws2811.c',
    'pwm.c',
    'pcm.c',
    'dma.c',
    'rpihw.c',
]

conf = configuration_data()
version_parts = meson.project_version().split('.')
conf.set('VERSION_MAJOR', version_parts[0])
conf.set('VERSION_MINOR', version_parts[1])
conf.set('VERSION_MICRO', version_parts[2])

headers = [
    'clk.h',
    'dma.h',
    'gpio.h',
    'mailbox.h',
    'pcm.h',
    'pwm.h',
    'rpihw.h',
    'ws2811.h',
]
version_h = configure_file(output: 'version.h',
                          configuration: conf)

headers += version_h

sources += headers

install_headers(headers)
rpi_ws2811_inc = include_directories('.')
rpi_ws2811_lib = library('rpi-ws2811', sources)
rpi_ws2811_dep = declare_dependency(link_with: [rpi_ws2811_lib],
                                    include_directories: [rpi_ws2811_inc])

test_sources = [
    'main.c'
]

text_exe = executable('rpi-ws2811-test', test_sources,
                      dependencies: [rpi_ws2811_dep])
test('rpi-ws2811', text_exe)