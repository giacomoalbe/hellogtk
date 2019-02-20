# Project name and programming language
project(
  'com.github.giacomoalbe.hellogtk',
  'vala',
  'c'
)

# Include i18n module
i18n = import('i18n')

# Set our translation domain
add_global_arguments(
  '-DGETTEXT_PACKAGE="@0@"'
    .format(
      meson.project_name(),
    ),
    language: 'c'
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

# Translate and install out .desktop file
i18n.merge_file(
  input: join_paths(
    'data',
    meson.project_name() + '.desktop.in'
  ),
  output: meson.project_name() + '.desktop',
  po_dir: join_paths(meson.source_root(), 'po'),
  type: 'desktop',
  install: true,
  install_dir: join_paths(
    get_option('datadir'), 'applications'
  )
)

# Translate and install out .appdata.xml file
i18n.merge_file(
  input: join_paths(
    'data',
    meson.project_name() + '.appdata.xml.in'
  ),
  output: meson.project_name() + '.appdata.xml',
  po_dir: join_paths(meson.source_root(), 'po'),
  install: true,
  install_dir: join_paths(
    get_option('datadir'), 'metainfo'
  )
)

subdir('po')
