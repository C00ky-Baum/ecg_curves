cmake_minimum_required( VERSION 3.10 )

project(curves)


# Gebraucht werden OpenGL und GLUT
find_package(OpenGL REQUIRED)
find_package(GLUT REQUIRED)


# Definition der Headerdateien
set(HEADERS
        include/abstract_curve.h
        include/application.h
        include/bezier_curve.h
        include/bspline.h
        include/control_points_editor.h
        include/curve_renderer.h
        include/hermite_spline.h
        include/lagrange_curve.h
        include/tiny_vec.h
        )

# Definition der Sourcedateien
set(SOURCES
        src/abstract_curve.cpp
        src/application.cpp
        src/bezier_curve.cpp
        src/bspline.cpp
        src/control_points_editor.cpp
        src/curve_renderer.cpp
        src/hermite_spline.cpp
        src/lagrange_curve.cpp
        src/main.cpp
        )

# Includeverzeichnisse setzen
include_directories(
        include
)


# Support fuer C++-11 aktivieren
set(CMAKE_CXX_STANDARD 11)

# Ziel hinzufuegen
add_executable(curves
        ${SOURCES}
        ${HEADERS}
        )

# Bibliotheken linken
target_link_libraries(curves
        OpenGL::GL
        OpenGL::GLU
        GLUT::GLUT
        )
