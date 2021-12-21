find_package(Qt${QT_MAJOR_VERSION} ${REQUIRED_QT_VERSION} CONFIG REQUIRED Widgets)

add_executable(kemoticonstest main.cpp)

target_link_libraries(kemoticonstest KF5::Emoticons Qt${QT_MAJOR_VERSION}::Widgets)
