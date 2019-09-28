##########################################################################################################################################
############################################################# TEMPLATE MODULE ############################################################
##########################################################################################################################################

# here some space to create optional base library targets

##########################################################################################################################################

set(PROTOC_SOURCE_CUSTOM ${GHOST_MODULE_TEMPLATE_ROOT_DIR}/protobuf/)
set(PROTOC_SOURCE_FILE ${GHOST_MODULE_TEMPLATE_ROOT_DIR}/protobuf/connection_grpc_robot.proto)
generate_protoc("${PROTOC_SOURCE_CUSTOM}" "${PROTOC_OUTPUT}" "${PROTOC_SOURCE_FILE}")

# module_minimum module
add_executable(connection_grpc_robot
	connection_grpc_robot.cpp
	${GHOST_MODULE_TEMPLATE_ROOT_DIR}/generated/connection_grpc_robot.pb.h
	${GHOST_MODULE_TEMPLATE_ROOT_DIR}/generated/connection_grpc_robot.pb.cc)
target_link_libraries(connection_grpc_robot ${CONAN_LIBS})

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
