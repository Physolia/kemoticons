kcoreaddons_add_plugin(emoticonstheme_adium
    INSTALL_NAMESPACE kf5/emoticonsthemes
)

target_sources(emoticonstheme_adium PRIVATE adium_emoticons.cpp adium_emoticons.h)

ecm_qt_declare_logging_category(emoticonstheme_adium
    HEADER kemoticons_plugin_adium_debug.h
    IDENTIFIER KEMOTICONS_PLUGIN_ADIUM
    CATEGORY_NAME kf.emoticons.adium
    OLD_CATEGORY_NAMES kf5.kemoticons.plugin_adium
    DESCRIPTION "kemoticons (plugin adium)"
    EXPORT KEMOTICONS
)

find_package(Qt${QT_MAJOR_VERSION}Xml REQUIRED)
target_link_libraries(emoticonstheme_adium
PRIVATE
    KF5::Emoticons
    Qt${QT_MAJOR_VERSION}::Xml # for QDomDocument
)

########### install files ###############

set_target_properties(emoticonstheme_adium PROPERTIES
    OUTPUT_NAME "adium"
)
# KF6: remove
install(
    FILES emoticonstheme_adium.desktop
    DESTINATION ${KDE_INSTALL_KSERVICESDIR}
)
