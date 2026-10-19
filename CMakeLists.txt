cmake_minimum_required(VERSION 3.26)

project(de-solver LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

find_package(Qt6 REQUIRED COMPONENTS Widgets)

qt_standard_project_setup()

file(GLOB CL_SRC components/client/src/*.cpp)
qt_add_executable(client
	${CL_SRC}
)

target_link_libraries(client PRIVATE
    Qt6::Widgets
)

file(GLOB EN_SRC components/engine/src/*.cpp)
add_executable(engine 
	${EN_SRC}
)

include(FetchContent)

FetchContent_Declare(
  thread-poollib
  GIT_REPOSITORY https://github.com/ms1d/thread-poollib
  GIT_TAG v1.0.0
)

FetchContent_MakeAvailable(thread-poollib)

target_link_libraries(engine PRIVATE
    thread-poollib
)
