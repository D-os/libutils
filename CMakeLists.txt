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
#set_target_properties(utils PROPERTIES LINKER_LANGUAGE C)

add_subdirectory(tests)
