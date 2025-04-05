SET(files_project
	main.cc
)
SOURCE_GROUP("project" FILES ${files_project})

SET(files_vulkan
	Vulkan/debug.cc
	Vulkan/debug.h
)
SOURCE_GROUP("vulkan" FILES ${files_vulkan})

SET(all_files_project ${files_project} ${files_vulkan})

SOURCE_GROUP("VulkanSandbox" FILES ${all_files_project})

ADD_EXECUTABLE(VulkanSandbox ${all_files_project})

target_link_libraries(VulkanSandbox PRIVATE Vulkan::Vulkan glfw glm::glm)

IF(MSVC)
    set_property(TARGET VulkanSandbox PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "${CMAKE_SOURCE_DIR}/bin")
ENDIF()