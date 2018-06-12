#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=uftrace
PKG_VERSION:=v0.8.3
PKG_RELEASE:=1
PKG_INSTALL:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/namhyung/uftrace.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)

PKG_MAINTAINER:=Benjamin Rauser <benjamin.rauser@gmx.net>
PKG_LICENSE:=GPL-2.0

PKG_FIXUP := autoreconf
CONFIGURE_VARS += ARCH="$(ARCH)"

include $(INCLUDE_DIR)/package.mk

define Package/uftrace
  SECTION:=utils
  CATEGORY:=Utilities
  URL:=https://github.com/linux-can/can-utils
  TITLE:=Tool to trace and analyze execution of a program
  DEPENDS:=libstdcpp +libelf1
endef

define Package/uftrace/install
	$(INSTALL_DIR)  $(1)/etc/bash_completion.d/
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/etc/bash_completion.d/* $(1)/etc/bash_completion.d/
	$(INSTALL_DIR)  $(1)/usr/lib/ $(1)/usr/bin/
	$(INSTALL_BIN)  $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
	$(INSTALL_BIN)  $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,uftrace))
