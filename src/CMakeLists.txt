
# Add source to this project's executable.
add_executable (vulkan_renderer
"main.cpp"
"vk_engine.cpp"
 "vk_engine.h" 
 "vk_types.h" 
 "vk_initializers.cpp" 
 "vk_initializers.h")


set_property(TARGET vulkan_renderer PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "$<TARGET_FILE_DIR:vulkan_renderer>")

target_include_directories(vulkan_renderer PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")

target_link_libraries(vulkan_renderer  vkbootstrap vma glm tinyobjloader imgui stb_image)

target_link_libraries(vulkan_renderer Vulkan::Vulkan sdl2)

add_dependencies(vulkan_renderer Shaders)