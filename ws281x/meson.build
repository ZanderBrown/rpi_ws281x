sources = [
    'mailbox.c',
    'ws2811.c',
    'pwm.c',
    'pcm.c',
    'dma.c',
    'rpihw.c',
]

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

install_headers(headers, subdir: 'ws281x')
rpi_ws281x_inc = include_directories('..')
rpi_ws281x_lib = library('rpi-ws281x', sources)
rpi_ws281x_dep = declare_dependency(link_with: [rpi_ws281x_lib],
                                    include_directories: [rpi_ws281x_inc])

pkg.generate(rpi_ws281x_lib)
