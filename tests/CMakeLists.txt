include_directories(
    "${EXTERNAL_GOOGLETEST_DIR}/googletest/include"
    "${EXTERNAL_GOOGLETEST_DIR}/googlemock/include"
)

add_executable(libutils_tests
        "BitSet_test.cpp"
        "LruCache_test.cpp"
        "Mutex_test.cpp"
#        "Singleton_test.cpp"
        "String8_test.cpp"
        "StrongPointer_test.cpp"
        "Unicode_test.cpp"
        "Vector_test.cpp"
        "Looper_test.cpp"
        "RefBase_test.cpp"
)

target_link_libraries(libutils_tests gtest_main gtest z utils)
