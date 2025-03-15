# Add all example subdirectories dynamically
file(GLOB EXAMPLE_DIRS LIST_DIRECTORIES true *)

foreach(EXAMPLE ${EXAMPLE_DIRS})
    if (IS_DIRECTORY ${EXAMPLE})
        add_subdirectory(${EXAMPLE})
    endif()
endforeach()