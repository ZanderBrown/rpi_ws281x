project('rpi-ws281x', 'c', version: '1.1.0')

pkg = import('pkgconfig')

conf = configuration_data()
version_parts = meson.project_version().split('.')
conf.set('VERSION_MAJOR', version_parts[0])
conf.set('VERSION_MINOR', version_parts[1])
conf.set('VERSION_MICRO', version_parts[2])

subdir('ws281x')
subdir('tests')
