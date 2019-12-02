add_executable(example example.cpp)

if(COORDGEN_BUILD_SHARED_LIBS)
    target_compile_definitions(example PRIVATE "BOOST_ALL_DYN_LINK")
else(COORDGEN_BUILD_SHARED_LIBS)
    set(Boost_USE_STATIC_LIBS ON)
    target_compile_definitions(example PRIVATE "STATIC_MAEPARSER")
    target_compile_definitions(example PRIVATE "STATIC_COORDGEN")
endif(COORDGEN_BUILD_SHARED_LIBS)

find_package(Boost COMPONENTS iostreams REQUIRED)

target_link_libraries(example coordgen Boost::iostreams)
