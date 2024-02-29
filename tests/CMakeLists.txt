# Test binary
add_executable(fontobene_qt_tests
    main.cpp
)

# Compiler defines
add_definitions(-DTESTFILEPATH="${CMAKE_CURRENT_SOURCE_DIR}/fonto.bene")

# Fail on warnings
target_compile_options(fontobene_qt_tests PRIVATE -Werror -Wall -Wextra)

# Linking
target_link_libraries(fontobene_qt_tests fontobene_qt Qt5::Core)

# Output binary name
set_target_properties(fontobene_qt_tests PROPERTIES OUTPUT_NAME fontobene-qt-tests)
