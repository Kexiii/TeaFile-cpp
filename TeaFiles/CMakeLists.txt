add_library(teafile)


file(GLOB_RECURSE DIR_CPPS CMAKE_CONFIGURE_DEPENDS "*.cpp")
target_sources(teafile PRIVATE ${DIR_CPPS})
target_compile_options(teafile PRIVATE -Wall -Werror -O3 -g -std=c++11)
target_include_directories(teafile PUBLIC ${PROJECT_SOURCE_DIR} ${Boost_INCLUDE_DIR})

install(TARGETS teafile LIBRARY DESTINATION lib)

install(DIRECTORY ${PROJECT_SOURCE_DIR}/TeaFiles
        DESTINATION include
        FILES_MATCHING
        PATTERN *.h)

install(DIRECTORY ${PROJECT_SOURCE_DIR}/TeaFiles
        DESTINATION include
        FILES_MATCHING
        PATTERN *.ipp)



