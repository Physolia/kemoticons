kcoreaddons_add_plugin(emoticonstheme_xmpp
    INSTALL_NAMESPACE kf5/emoticonsthemes
)

target_sources(emoticonstheme_xmpp PRIVATE xmpp_emoticons.cpp xmpp_emoticons.h)

ecm_qt_declare_logging_category(emoticonstheme_xmpp
    HEADER kemoticons_plugin_xmpp_debug.h
    IDENTIFIER KEMOTICONS_PLUGIN_XMPP
    CATEGORY_NAME kf.emoticons.xmpp
    OLD_CATEGORY_NAMES kf5.kemoticons.plugin_xmpp
    DESCRIPTION "kemoticons (plugin xmpp)"
    EXPORT KEMOTICONS
)


find_package(Qt${QT_MAJOR_VERSION}Xml REQUIRED)
target_link_libraries(emoticonstheme_xmpp
PRIVATE
    KF5::Emoticons
    Qt${QT_MAJOR_VERSION}::Xml # for QDomDocument
)

########### install files ###############

set_target_properties(emoticonstheme_xmpp PROPERTIES
    OUTPUT_NAME "xmpp"
)

# KF6: remove
install(
    FILES emoticonstheme_xmpp.desktop
    DESTINATION ${KDE_INSTALL_KSERVICESDIR}
)
