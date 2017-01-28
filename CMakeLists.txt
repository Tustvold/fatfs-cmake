if (NOT DEFINED ChibiOS_INCLUDE_DIRS)
    message(FATAL_ERROR "ChibiOS not found")
endif ()

add_library(fatfs
        src/ff.c
        src/option/unicode.c
        ${CHIBIOS_ROOT}/os/various/fatfs_bindings/fatfs_diskio.c
        ${CHIBIOS_ROOT}/os/various/fatfs_bindings/fatfs_syscall.c
        )

target_include_directories ( fatfs PUBLIC
        ${ChibiOS_INCLUDE_DIRS}
        ${CMAKE_CURRENT_SOURCE_DIR}/src
)