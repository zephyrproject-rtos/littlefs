if(CONFIG_FILE_SYSTEM_LITTLEFS)
add_library(LITTLEFS INTERFACE)

target_include_directories(LITTLEFS INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

zephyr_library()
zephyr_library_sources(
    lfs.c
    lfs_util.c
    )
zephyr_library_link_libraries(LITTLEFS)
target_link_libraries(LITTLEFS INTERFACE zephyr_interface)
endif()
