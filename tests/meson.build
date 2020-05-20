test_sources = [
    'main.c'
]

text_exe = executable('rpi-ws2811-test', test_sources,
                      dependencies: [rpi_ws281x_dep])
test('rpi-ws2811', text_exe)