include_directories(
     /usr/local/include
)
link_directories(
     /usr/local/lib
)
set(libraries
    logger
)

set(examples
    logger_console_example
    logger_file_example
    logger_multi_example
    loggerconf_example
)
include_directories(
    ${PROJECT_SOURCE_DIR}/src
)
foreach(example IN LISTS examples)
    add_executable(${example} ${example}.c)
    target_link_libraries(${example} ${libraries})
endforeach()
