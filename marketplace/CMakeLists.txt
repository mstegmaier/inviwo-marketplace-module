ivw_module(Marketplace)

find_package(Qt5Core QUIET REQUIRED)

set(HEADER_FILES
    include/inviwo/marketplace/marketplacemodule.h
    include/inviwo/marketplace/marketplacemoduledefine.h
    include/inviwo/marketplace/processors/marketplace.h
)
ivw_group("Header Files" ${HEADER_FILES})

set(SOURCE_FILES
    src/marketplacemodule.cpp
    src/processors/marketplace.cpp
)
ivw_group("Source Files" ${SOURCE_FILES})

set(SHADER_FILES
	# Add shaders
)
ivw_group("Shader Files" ${SHADER_FILES})

set(TEST_FILES
    tests/unittests/marketplace-unittest-main.cpp
)
ivw_add_unittest(${TEST_FILES})

ivw_create_module(${SOURCE_FILES} ${HEADER_FILES} ${SHADER_FILES})
target_link_libraries(inviwo-module-marketplace PRIVATE Qt5::Core)

# Add shader directory to install package
#ivw_add_to_module_pack(${CMAKE_CURRENT_SOURCE_DIR}/glsl)
