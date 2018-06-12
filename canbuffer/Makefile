#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=canutils-library
PKG_VERSION:=1.0.1
PKG_RELEASE=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/berauser/canutils.git
PKG_SOURCE_VERSION:=release_canutils_$(PKG_VERSION)

PKG_MAINTAINER:=Benjamin Rauser <benjamin.rauser@gmx.net>
PKG_LICENSE:=GPL-2.1

PATCH_DIR := patches-$(LIBC)

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/canutils-library
  SECTION:=utils
  CATEGORY:=Utilities
  URL:=https://github.com/linux-can/can-utils
  TITLE:=C++ library for accessing the CAN bus
  DEPENDS:=libstdcpp
endef

define Build/InstallDev
	$(INSTALL_DIR)  $(1)/usr/lib/
	$(INSTALL_BIN)  $(PKG_INSTALL_DIR)/usr/lib/libcanutils.so* $(1)/usr/lib/
	$(INSTALL_BIN)  $(PKG_INSTALL_DIR)/usr/lib/libnetlink.so*  $(1)/usr/lib/
	
	$(INSTALL_DIR)  $(1)/usr/include/canutils/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/include/canutils/*  $(1)/usr/include/canutils/
endef

define Package/canutils-library/install
	$(INSTALL_DIR) $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/libcanutils.so* $(1)/usr/lib/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/libnetlink.so*  $(1)/usr/lib/
endef

$(eval $(call BuildPackage,canutils-library))
