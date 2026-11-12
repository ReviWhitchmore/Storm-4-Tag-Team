cmake_minimum_required(VERSION 3.20)
project(Storm4TagTeam LANGUAGES C CXX ASM_MASM)

# Storm 4 Tag Team v0.8 - proxy winmm.dll for NARUTO SHIPPUDEN: Ultimate Ninja STORM 4 (64-bit).
if(NOT CMAKE_SIZEOF_VOID_P EQUAL 8)
  message(FATAL_ERROR "Storm 4 is a 64-bit game: use the x64 MSVC toolchain.")
endif()

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_MSVC_RUNTIME_LIBRARY "MultiThreaded$<$<CONFIG:Debug>:Debug>")

# MinHook (BSD 2-Clause, see third_party/minhook/LICENSE.txt)
set(MINHOOK_DIR "${CMAKE_SOURCE_DIR}/third_party/minhook" CACHE PATH "MinHook source folder")
add_library(minhook STATIC
  ${MINHOOK_DIR}/src/buffer.c
  ${MINHOOK_DIR}/src/hook.c
  ${MINHOOK_DIR}/src/trampoline.c
  ${MINHOOK_DIR}/src/hde/hde64.c
)
target_include_directories(minhook PUBLIC ${MINHOOK_DIR}/include)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

# The game loads winmm.dll from its own folder before main(); the proxy forwards every export to the system DLL.
add_library(storm6 SHARED
  src/dllmain.cpp
  src/census.cpp
  src/addresses.cpp
  src/promote.cpp
  src/input.cpp
  src/hud.cpp
  src/menu.cpp
  src/settings.cpp
  src/pads.cpp
  src/ult.cpp
  src/chronicles.cpp
  src/scene_probe.cpp
  src/chronicles_balance.cpp
  src/cpu_adapt.cpp
  src/parry.cpp
  src/grab_defense.cpp
  src/perfect_sub.cpp
  src/jutsu_clash.cpp
  src/jutsu_clash_3d.cpp
  src/dual_combo.cpp
  src/wall_run.cpp
  src/frame_capture.cpp
  src/trailer_cam.cpp
  src/lang.cpp
  src/fighter_motion.cpp
  src/scene_thunk.asm
  src/camera.cpp
  src/proxy/proxy.cpp
  src/proxy/winmm_exports.asm
  src/proxy/winmm.def
)
set_target_properties(storm6 PROPERTIES OUTPUT_NAME winmm)
target_link_libraries(storm6 PRIVATE minhook d3d11 dxgi d3dcompiler windowscodecs ole32)
target_compile_definitions(storm6 PRIVATE WIN32_LEAN_AND_MEAN NOMINMAX UNICODE _UNICODE)
target_compile_options(storm6 PRIVATE $<$<COMPILE_LANGUAGE:CXX>:/utf-8>)
