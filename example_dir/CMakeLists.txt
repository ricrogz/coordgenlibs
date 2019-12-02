add_executable(example example.cpp)

if(NOT COORDGEN_BUILD_SHARED_LIBS)
    target_compile_definitions(example PRIVATE "STATIC_MAEPARSER")
    target_compile_definitions(example PRIVATE "STATIC_COORDGEN")
endif(NOT COORDGEN_BUILD_SHARED_LIBS)

target_link_libraries(example coordgen)
