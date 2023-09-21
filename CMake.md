# [[CMake Standard Template]] for the impatient

# What is CMake
CMake is a cross platform build generator. 
It follows us to
+ Structure and build C/C++ projects
+ Integrate third-party dependencies
+ Orchestrate tests
+ Package projects

Any CMake project requires a CMakeLists.txt which is like a requirements.txt used by pip.

# Root CMakeLists.txt
```CMake
cmake_minimum_required(VERSION 3.15)
project(<project_name>)


add_executable(<name_of_executable> <files_to_be_compiled>)
```

>[!info]
>Make separate directories for include, source files and example in any C++ project.

The root CMakeLists file must not have anything involved with building the project, but rather this has to be outsourced to the include, src, and example directories. The root CMakeLists just adds the subdirectories which runs the CMake files inside the respective directoies.

```CMake
cmake_minimum_required(VERSION 3.15)
project(<project_name>)

add_subdirectory(include)
add_subdirectory(src)

option(BUILD_EXAMPLES "Whether or not to build examples" ON)

if(BUILD_EXAMPLES)
	message(STATUS "Building examples...")
	add_subdirectory(example)
endif()
```

# [[include CMakeLists.txt]]
# [[src CMakeLists.txt]]
# [[example CMakeLists.txt]]