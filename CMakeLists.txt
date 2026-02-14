cmake_minimum_required(VERSION 3.21)
project(ParametricViewer LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenCASCADE CONFIG REQUIRED)
find_package(Coin CONFIG REQUIRED)
find_package(SoQt CONFIG REQUIRED)

add_executable(ParametricViewer
    src/Main/main.cpp
    src/Base/ParametricSolid.cpp
    src/Gui/ViewProvider.cpp
    src/Gui/OccToCoin.cpp
)

target_link_libraries(ParametricViewer
    PRIVATE
        OpenCASCADE::OpenCASCADE
        Coin::Coin
        SoQt::SoQt
)