##########################################################################################################################################
############################################################# TEMPLATE MODULE ############################################################
##########################################################################################################################################

# here some space to create optional base library targets

##########################################################################################################################################

# module_minimum module
add_executable(module_minimum module_minimum.cpp)
target_link_libraries(module_minimum ${CONAN_LIBS_GHOSTMODULE})

##### Unit tests #####

if ((DEFINED BUILD_TESTS) AND (${BUILD_TESTS}))
# 	file(GLOB source_tests
# 		${GHOST_MODULE_TEMPLATE_ROOT_DIR}/tests/SomeTests.cpp
# 	)

# 	add_executable(template_tests ${source_tests})
# 	target_link_libraries(template_tests ${CONAN_LIBS_GHOSTMODULE} ${CONAN_LIBS_GTEST})

# 	gtest_add_tests(TARGET template_tests)

# 	set_property(TARGET template_tests PROPERTY FOLDER "tests")
endif()
