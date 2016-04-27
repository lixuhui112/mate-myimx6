# Copyright (C) 2013-2015 Freescale Semiconductor
# Released under the MIT license (see COPYING.MIT for the terms)

SUMMARY = "Linux Kernel provided and supported by Freescale"
DESCRIPTION = "Linux Kernel provided and supported by Freescale with focus on \
i.MX Family Reference Boards. It includes support for many IPs such as GPU, VPU and IPU."

require recipes-kernel/linux/linux-imx.inc
require recipes-kernel/linux/linux-dtb.inc

DEPENDS += "lzop-native bc-native"

#/*********分支branch名称************/
SRCBRANCH = "myimx6"  
#/*********本地内核命名********/  
LOCALVERSION = "linux-4.1.15-r0" 
#/*****head,在branch分支中.git/reaf/head/(当前分支)***/
SRCREV = "b5fcae7202e8baf1ebc0260e6dd518ca763e66fb" 
#/******源码所在github网站地址************/ 
KERNEL_SRC ?= "git://github.com/lixuhui112/myimx6-linux.git;" 
SRC_URI = "${KERNEL_SRC};branch=${SRCBRANCH}"

DEFAULT_PREFERENCE = "1"

addtask copy_defconfig after do_unpack before do_configure
do_copy_defconfig () {
    # copy latest imx_v7_defconfig to use
    cp ${S}/arch/arm/configs/imx_v7_defconfig ${B}/.config
    cp ${S}/arch/arm/configs/imx_v7_defconfig ${B}/../defconfig
}

COMPATIBLE_MACHINE = "(mx6|mx6ul|mx7|myimx6)"
