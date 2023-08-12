# Set a minimum required CMake version to build in case CMake wouldn't build just cause you didn't
cmake_minimum_required(VERSION 3.10)

# Give the project a unique identifier, so CMake knows what to name build files by default
project(TextTo3d)

# Set the path to the wxWidgets library
set(wxWidgets_ROOT_DIR C:/Users/Anumudu/Downloads/wxWidgets-3.2.2.1)

# Include the wxWidgets configuration
find_package(wxWidgets COMPONENTS core base)

# Include the wxWidgets use file to set up compiler flags, etc.
include(${wxWidgets_USE_FILE})

# Specify the name of the exe and add the entry point of the entire application
add_executable(TextTo3d src/main.cpp)

target_include_directories(TextTo3d PRIVATE ${wxWidgets_INCLUDE_DIRS})

# Link against the wxWidgets libraries
target_link_libraries(TextTo3d PRIVATE ${wxWidgets_LIBRARIES}) 