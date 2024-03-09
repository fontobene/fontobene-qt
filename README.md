# C++/Qt FontoBene Parser

A header-only library to parse FontoBene stroke fonts with C++11/Qt.

Successor of `fontobene-qt5`, now supporting both Qt5 and Qt6.

## Installing

    $ mkdir build && cd build
    $ cmake .. -DCMAKE_INSTALL_PREFIX=/usr
    $ make -j8
    $ tests/fontobene-qt-tests
    $ make install

## Qt Version

By default the used Qt version is automatically detected by CMake while Qt6
is preferred over Qt5. To explicitly specify the Qt version to use, set the
CMake variable `FONTOBENE_QT_MAJOR_VERSION` to either `5` or `6`:

    $ cmake .. -DFONTOBENE_QT_MAJOR_VERSION=5

## pkg-config

If you're packaging fontobene-qt and want an example pkg-config file, check
out `fontobene-qt-5.pc.example` (for Qt5) and `fontobene-qt-6.pc.example`
(for Qt6). Both should be provided to let users choose the Qt version.
Depending on your distro, the `includedir` might need adjusting.

## License

Licensed under either of

- Apache License, Version 2.0, ([LICENSE-APACHE](LICENSE-APACHE) or
  http://www.apache.org/licenses/LICENSE-2.0)
- MIT license ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.
