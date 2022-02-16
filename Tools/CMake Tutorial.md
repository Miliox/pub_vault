
# Sample

```cmake
# CMakeLists.txt
cmake_minimum_required(VERSION 3.20)

project(given-name
        VERSION      0.0.1.0
		DESCRIPTION  ""
		HOMEPAGE_URL ""
		LANGUAGES    CXX)

list(APPEND CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake")

set(CMAKE_CXX_STANDARD          20)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS        YES)

set(CMAKE_POSITION_INDEPENDENT_CODE       YES)
set(CMAKE_INTERPROCEDURAL_OPTIMIZATION    YES)

```

```cmake
# cmake/prevent_inplace_builds.cmake
file(TO_CMAKE_PATH "${PROJECT_BINARY_DIR}/CMakeLists.txt" LOCATION_PATH)
if(EXISTS "${LOCATION_PATH}")
	set(LINE1 "It cannot build in a source directory.")
	set(LINE2 "Please make a build subdirectory.")
	set(LINE3 "Feel free to remove CMakeCache.txt and CMakeFiles.")
    message(FATAL_ERROR "${LINE1}\n${LINE2}\n${LINE3}")
endif()
```

```cmake
# cmake/enable_warnings.cmake
if((CMAKE_CXX_COMPILER_ID MATCHES "Clang") OR
   (CMAKE_CXX_COMPILER_ID MATCHES "GNU"))
    # basic
    add_compile_options(-Wall)
    add_compile_options(-Werror)
    add_compile_options(-Wextra)
	add_compile_options(-Wshadow)
	add_compile_options(-Wnon-virtual-dtor)
	add_compile_options(-pedantic)

    # recommended
	add_compile_options(-Wconversion)
	add_compile_options(-Wdouble-promotion)
	add_compile_options(-Wduplicated-branches)
	add_compile_options(-Wduplicated-cond)
	add_compile_options(-Wformat=2)
	add_compile_options(-Wlifetime)
	add_compile_options(-Wlogical-op)
	add_compile_options(-Wmisleading-identation)
	add_compile_options(-Wnull-dereference)
	add_compile_options(-Wold-style-cast)
	add_compile_options(-Woverloaded-virtual)
	add_compile_options(-Wpedantic)
	add_compile_options(-Wsign-conversion)
	add_compile_options(-Wunused)

	# catch all (maybe too much!)
	add_compile_options(-Weverything)
	add_compile_options(-Weffc++)

elseif(CMAKE_CXX_COMPILER_ID MATCHES "MSVC")
	# basics
	add_compile_options(/permissive)
	add_compile_options(/W4)
	add_compile_options(/w14640)

	# recommended
	add_compile_options(/w14242)
	add_compile_options(/w14254)
	add_compile_options(/w14263)
	add_compile_options(/w14265)
	add_compile_options(/w14287)
	add_compile_options(/w14289)
	add_compile_options(/w14296)
	add_compile_options(/w14311)
	add_compile_options(/w14545)
	add_compile_options(/w14546)
	add_compile_options(/w14547)
	add_compile_options(/w14549)
	add_compile_options(/w14555)
	add_compile_options(/w14619)
	add_compile_options(/w14640)
	add_compile_options(/w14826)
	add_compile_options(/w14905)
	add_compile_options(/w14928)
endif()
```