project (Examples CXX)

function (ADD_EXAMPLE _NAME)
  set (_EXE_NAME ${_NAME}.exe)
  add_executable (${_EXE_NAME} ./${_NAME}/main.cpp)
  target_link_libraries (${_EXE_NAME} scattering)
  set_target_properties (${_EXE_NAME} PROPERTIES RUNTIME_OUTPUT_DIRECTORY bin/)
  add_dependencies (examples ${_EXE_NAME})
endfunction()

include_directories (${CMAKE_SOURCE_DIR}/include/)
add_custom_target (examples)

ADD_EXAMPLE (tully_1)
ADD_EXAMPLE (tully_1_range)
ADD_EXAMPLE (tully_1_print)
ADD_EXAMPLE (tully_1_check)
ADD_EXAMPLE (tully_2)
ADD_EXAMPLE (tully_2_range)
ADD_EXAMPLE (tully_3)
ADD_EXAMPLE (tully_3_range)
