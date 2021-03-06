How to create the installation CD

1) Prepare your system

You need to export ZINSTALLER_ADDRESS and ZINSTALLER_KEYID on your ~/.bashrc
You can find commented examples in build_cd.conf

WARNING: debootstrap will fail over cryptfs mount points.

2) Run ./autobuild

You will need to download the Ubuntu Server installers to remaster as you'll
be prompted to select them at the beginning of the generation process.
If you are not on a X11 environment, you'll have to copy them manually to
the build directory under ../build_installer.

3) Put extra ubuntu packages (optional, for custom installers only)

You can put the packages you want included in the installer in the
'extra-packages.list' file and then use 'generate_extras.sh' script to get them
and their dependencies on a chrooted debootstrap environment.

You can also edit the sources.list file if you want to fetch the packages
from external repositories instead of manually copying the .deb files.

You can use 'build_cd.sh' inside a build directory to regenerate the ISO
image replacing the whole 'extras' directory.

Aditionally, if you want to include locally built packages, you can create
a custom-extra-packages directory with three subdirectories for the
different architectures: i386, amd64 and all.
