cmake_minimum_required(VERSION 2.4)
set(CMAKE_BUILD_TYPE release)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
find_package(Boost REQUIRED COMPONENTS program_options system-mt)
include_directories(. ../misc)
add_executable(
	xbt_client_cli
	../misc/bt_misc.cpp
	../misc/bvalue.cpp
	../misc/socket.cpp
	../misc/virtual_binary.cpp
	../misc/xcc_z.cpp
	"XBT Client Command Line Interface.cpp"
)

target_link_libraries(xbt_client_cli z boost_system-mt boost_program_options)
