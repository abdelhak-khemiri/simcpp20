include(FetchContent)

FetchContent_Declare(Catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2
  GIT_TAG        97c48e0c343d26d50764fafdc90b1e630fbd10ce) # v3.1.0
FetchContent_MakeAvailable(Catch2)

add_executable(tests tests.cpp)
target_link_libraries(tests PRIVATE
  fschuetz04::simcpp20
  Catch2::Catch2WithMain)

if(CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
  target_compile_options(tests PRIVATE -Wall -Wextra)
endif()
