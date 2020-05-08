= FSL Community Yocto Vnet for Wandboard IMX6DL Rev D1

To get the BSP you need to have `repo` installed and use it as:

Install the `repo` utility:

[source,console]
$: mkdir ~/bin
$: curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
$: chmod a+x ~/bin/repo

Download the BSP source:

[source,console]
$: PATH=${PATH}:~/bin
$: mkdir fsl-community-bsp
$: cd fsl-community-bsp
$: repo init -u https://github.com/vnet-huanvh/vnet-linux.git -b vnet-imx6-4.9.11_1.0.0_ga
$: repo sync

== Configurations for setup script

`“MACHINE”` is the target of build. It usually corresponds to the name of SOM or SBC.

`“-b”` specify the build directory.

`“-e”` sets the graphical back end for frame buffer and direct fb images. X11 is default if no backend is set.

== Build Yocto for TechNexion target platform
=== For Wandboard IMX6DL Rev D1

*Wandboard IMX6DL Rev D1:*
[source,console]
$: MACHINE=vnet-wandboard source vnet-setup-release.sh -b build-wandboard -e x11
$: bitbake core-image-base
