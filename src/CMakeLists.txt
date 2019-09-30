# Set minimum CMake version
cmake_minimum_required(VERSION 3.0.0)

# Give the project a name
project(JobCreator)

# create libraries and include header files
add_library(utils utils/input.c)
target_include_directories(utils PUBLIC include)
add_library(job job/job.c)
target_include_directories(job PUBLIC include)

# add job creator executable and link libraries
add_executable(jobcreator main.c)
target_link_libraries(jobcreator utils job)
