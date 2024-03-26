# Changelog

This project follows semantic versioning.

Possible log types:

- `[added]` for new features.
- `[changed]` for changes in existing functionality.
- `[deprecated]` for once-stable features removed in upcoming releases.
- `[removed]` for deprecated features removed in this release.
- `[fixed]` for any bug fixes.
- `[security]` to invite users to upgrade in case of vulnerabilities.


### 1.0.0 (2024-03-27)

First release after renaming the library. Changes compared to
`fontobene-qt5` v0.2.0:

- [added] Support building with Qt6
- [added] Support choosing Qt version with variable `FONTOBENE_QT_MAJOR_VERSION`
- [added] Provide assignment operator for `Font` struct
- [changed] Rename CMake target to `fontobene_qt`
- [changed] Rename include directory to `fontobene-qt`
- [changed] Rename pkg-config files (Qt version number as suffix)
- [removed] Drop support for `qmake` build system
