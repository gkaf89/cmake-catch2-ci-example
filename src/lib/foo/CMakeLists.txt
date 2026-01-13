add_library(foo STATIC src/foo.cpp)

target_include_directories(foo
        PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        $<INSTALL_INTERFACE:include>
)

target_sources(foo PUBLIC
    FILE_SET headers
    TYPE HEADERS
    BASE_DIRS include
    FILES include/foo/foo.hpp)

install(TARGETS foo
        EXPORT fooConfig
        ARCHIVE DESTINATION lib
        LIBRARY DESTINATION lib
        RUNTIME DESTINATION bin
        INCLUDES DESTINATION include
        FILE_SET headers DESTINATION include
)

install(EXPORT fooConfig DESTINATION share/cmake)
