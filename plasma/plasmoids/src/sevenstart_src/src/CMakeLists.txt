# TODO: adapt "org.kde.plasma" here & elsewhere if needed (see README)
add_definitions(-DTRANSLATION_DOMAIN=\"plasma_applet_io.gitgud.wackyideas.SevenStart\")



set(SevenStart_SRCS
    SevenStart.cpp
    dialogshadows.cpp
)

add_library(io.gitgud.wackyideas.SevenStart MODULE ${SevenStart_SRCS})

target_link_libraries(io.gitgud.wackyideas.SevenStart
                      Qt6::Gui
                      Qt6::Quick
                      KF6::I18n
                      KF6::WindowSystem
                      KF6::Kirigami
                      Plasma
                      PlasmaQuick
                      KF6::Svg
                      KF6::ConfigCore
                      KF6::ConfigGui
                      KF6::CoreAddons)


#target_link_libraries(plasma_applet_seventasks KF5::WindowSystem)
include_directories(${CMAKE_INSTALL_PREFIX}/include/Plasma ${CMAKE_INSTALL_PREFIX}/include/KF6/KConfigCore/ ${CMAKE_INSTALL_PREFIX}/include/KF6/KConfig/ ${CMAKE_INSTALL_PREFIX}/include/KF6/KCoreAddons/ ${CMAKE_INSTALL_PREFIX}/include/PlasmaQuick/)

install(TARGETS io.gitgud.wackyideas.SevenStart DESTINATION ${KDE_INSTALL_PLUGINDIR}/plasma/applets)


#plasma_install_package(package io.gitgud.wackyideas.SevenStart)
