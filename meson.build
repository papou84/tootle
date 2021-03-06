project('com.github.bleakgrey.tootle', 'vala', 'c')

gnome = import('gnome')
i18n = import('i18n')

add_global_arguments([
        '-DGETTEXT_PACKAGE="@0@"'.format(meson.project_name())
    ],
    language: 'c',
)

asresources = gnome.compile_resources(
  'as-resources', 'data/' + meson.project_name() + '.gresource.xml',
  source_dir: 'data',
  c_name: 'as'
)

executable(
    meson.project_name(),
    asresources,
    'src/Application.vala',
    'src/MainWindow.vala',
    'src/SettingsManager.vala',
    'src/AccountManager.vala',
    'src/NetManager.vala',
    'src/Utils.vala',
    'src/CmdRunner.vala',
    'src/API/Account.vala',
    'src/API/Relationship.vala',
    'src/API/Mention.vala',
    'src/API/Tag.vala',
    'src/API/Status.vala',
    'src/API/StatusVisibility.vala',
    'src/API/Notification.vala',
    'src/API/NotificationType.vala',
    'src/API/Attachment.vala',
    'src/Widgets/HeaderBar.vala',
    'src/Widgets/AlignedLabel.vala',
    'src/Widgets/RichLabel.vala',
    'src/Widgets/AccountsButton.vala',
    'src/Widgets/StatusWidget.vala',
    'src/Widgets/NotificationWidget.vala',
    'src/Widgets/AttachmentWidget.vala',
    'src/Widgets/AttachmentBox.vala',
    'src/Dialogs/PostDialog.vala',
    'src/Views/AbstractView.vala',
    'src/Views/AddAccountView.vala',
    'src/Views/HomeView.vala',
    'src/Views/LocalView.vala',
    'src/Views/FederatedView.vala',
    'src/Views/NotificationsView.vala',
    'src/Views/StatusView.vala',
    'src/Views/AccountView.vala',
    'src/Views/FavoritesView.vala',
    dependencies: [
        dependency('gtk+-3.0'),
        dependency('glib-2.0', version: '>=2.30.0'),
        dependency('granite'),
        dependency('json-glib-1.0'),
        dependency('libsoup-2.4')
    ],
    install: true
)

subdir('data')
subdir('po')

meson.add_install_script('meson/post_install.py')
