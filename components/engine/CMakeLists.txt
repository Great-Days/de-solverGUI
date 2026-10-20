cmake_minimum_required(VERSION 3.26)

file(GLOB EN_SRC src/*.cpp)
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
