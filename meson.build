# Project name and programming language
project(
  'com.github.giacomoalbe.hellogtk',
  'vala',
  'c'
)

# Create a new executable
# List file we want to compile
# List dependencies
# Install
executable(
  meson.project_name(),
  'src/Application.vala',
  dependencies: [
    dependency('gtk+-3.0')
  ],
  install: true
)

# Install .desktop file so the Application Menu will see it
install_data(
  join_paths('data', meson.project_name() + '.desktop'),
  install_dir: join_paths(get_option('datadir'), 'applications')
)

# Install .appdata.xml file so AppCenter will see it
install_data(
  join_paths('data', meson.project_name() + '.appdata.xml'),
  install_dir: join_paths(get_option('datadir'), 'metainfo')
)
