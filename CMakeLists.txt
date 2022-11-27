project(imgui)

add_library(imgui
	STATIC
	imconfig.h
	imgui.cpp
	imgui.h
	imgui_demo.cpp
	imgui_draw.cpp
	imgui_internal.h
	imgui_tables.cpp
	imgui_widgets.cpp
	imstb_rectpack.h
	imstb_textedit.h
	imstb_truetype.h

	#ER TODO, this cmakelists should be dynamic in which backend(s) it compiles, rather than just defaulting to opengl3/glfw,
	# then parent can control its compilation...but this works for now.

	#	backends/imgui_impl_allegro5.cpp
	#	backends/imgui_impl_allegro5.h
	#	backends/imgui_impl_android.cpp
	#	backends/imgui_impl_android.h
	#	backends/imgui_impl_dx9.cpp
	#	backends/imgui_impl_dx9.h
	#	backends/imgui_impl_dx10.cpp
	#	backends/imgui_impl_dx10.h
	#	backends/imgui_impl_dx11.cpp
	#	backends/imgui_impl_dx11.h
	#	backends/imgui_impl_dx12.cpp
	#	backends/imgui_impl_dx12.h
	backends/imgui_impl_glfw.cpp
	backends/imgui_impl_glfw.h
	#	backends/imgui_impl_glut.cpp
	#	backends/imgui_impl_glut.h
	#	backends/imgui_impl_metal.h
	#	backends/imgui_impl_metal.mm
	#	backends/imgui_impl_opengl2.cpp
	#	backends/imgui_impl_opengl2.h
	backends/imgui_impl_opengl3.cpp
	backends/imgui_impl_opengl3.h
	#	backends/imgui_impl_opengl3_loader.h
	#	backends/imgui_impl_osx.h
	#	backends/imgui_impl_osx.mm
	#	backends/imgui_impl_sdl.cpp
	#	backends/imgui_impl_sdl.h
	#	backends/imgui_impl_sdlrenderer.cpp
	#	backends/imgui_impl_sdlrenderer.h
	#	backends/imgui_impl_vulkan.cpp
	#	backends/imgui_impl_vulkan.h
	#	backends/imgui_impl_wgpu.cpp
	#	backends/imgui_impl_wgpu.h
	#	backends/imgui_impl_win32.cpp
	#	backends/imgui_impl_win32.h
	)

target_link_libraries(imgui
	glfw
	)

target_include_directories(imgui
	PUBLIC
	${PROJECT_SOURCE_DIR}
	${PROJECT_SOURCE_DIR}/backends
	)

#[[get_target_property(IMGUI_INCLUDES imgui INCLUDE_DIRECTORIES)
message(WARNING "${IMGUI_INCLUDES}")]]
