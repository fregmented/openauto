add_executable(btservice
        AndroidBluetoothServer.cpp
        AndroidBluetoothService.cpp
        btservice.cpp
        ${CMAKE_SOURCE_DIR}/include/btservice/AndroidBluetoothServer.hpp
        ${CMAKE_SOURCE_DIR}/include/btservice/AndroidBluetoothService.hpp
        ${CMAKE_SOURCE_DIR}/include/btservice/IAndroidBluetoothServer.hpp
        ${CMAKE_SOURCE_DIR}/include/btservice/IAndroidBluetoothService.hpp
        )

target_include_directories(btservice PRIVATE
        ${CMAKE_SOURCE_DIR}/include
        )

target_link_libraries(btservice
        Threads::Threads
        ${Boost_LIBRARIES}
        openauto
       )

set_target_properties(btservice
        PROPERTIES INSTALL_RPATH_USE_LINK_PATH 1)

install(TARGETS btservice
        RUNTIME DESTINATION bin)
