include_directories(
#    "${ANDROID_LIBNATIVEHELPER_DIR}/include/nativehelper"
    "${EXTERNAL_SAFE_IOP_DIR}/include"
)

add_definitions("-DLIBUTILS_NATIVE=1")

add_library(utils SHARED
        "FileMap.cpp"
        "JenkinsHash.cpp"
#        "NativeHandle.cpp"
        "Printer.cpp"
        "PropertyMap.cpp"
        "RefBase.cpp"
        "SharedBuffer.cpp"
        "StopWatch.cpp"
        "String8.cpp"
        "String16.cpp"
        "StrongPointer.cpp"
        "SystemClock.cpp"
        "Threads.cpp"
        "Timers.cpp"
        "Tokenizer.cpp"
        "Unicode.cpp"
        "VectorImpl.cpp"
        "misc.cpp"
        "Looper.cpp"
        "CallStack.cpp"
        "ProcessCallStack.cpp"
)
target_link_libraries(utils cutils dl)

include_directories(
    "${EXTERNAL_GOOGLETEST_DIR}/googletest/include"
    "${EXTERNAL_GOOGLETEST_DIR}/googlemock/include"
)

add_executable(libutils_tests
        "BitSet_test.cpp"
        "FileMap_test.cpp"
        "LruCache_test.cpp"
        "Mutex_test.cpp"
        "SharedBuffer_test.cpp"
        "String8_test.cpp"
        "StrongPointer_test.cpp"
        "Unicode_test.cpp"
        "Vector_test.cpp"
                "Looper_test.cpp"
                "RefBase_test.cpp"
)

target_link_libraries(libutils_tests gtest_main gtest z base utils)
