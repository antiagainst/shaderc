if(${SHADERC_ENABLE_TESTS})
  if(${SHADERC_ENABLE_SPVC_PARSER})
    add_test(NAME spvc_spirv_cross_tests
      COMMAND ${PYTHON_EXECUTABLE}
      ${CMAKE_CURRENT_SOURCE_DIR}/run_spirv_cross_tests.py
      $<TARGET_FILE:spvc_exe>
      $<TARGET_FILE:spirv-as>
      $<TARGET_FILE:spirv-opt>
      $<TARGET_FILE:glslangValidator>
      ${SHADERC_SPIRV_CROSS_DIR}
      ${CMAKE_CURRENT_SOURCE_DIR}
      --run-spvc-tests)
  else()
    add_test(NAME spvc_spirv_cross_tests
      COMMAND ${PYTHON_EXECUTABLE}
      ${CMAKE_CURRENT_SOURCE_DIR}/run_spirv_cross_tests.py
      $<TARGET_FILE:spvc_exe>
      $<TARGET_FILE:spirv-as>
      $<TARGET_FILE:spirv-opt>
      $<TARGET_FILE:glslangValidator>
      ${SHADERC_SPIRV_CROSS_DIR}
      ${CMAKE_CURRENT_SOURCE_DIR})
  endif()
endif()
