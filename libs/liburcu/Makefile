#
# Copyright (C) 2015 OpenWrt.org
# Copyright (C) 2014-2018 CZ.NIC, z.s.p.o. <knot-dns@labs.nic.cz>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=liburcu
PKG_VERSION:=0.11.1
PKG_RELEASE:=1

PKG_MAINTAINER:=Daniel Salzman <daniel.salzman@nic.cz>
PKG_LICENSE:=LGPL-2.1-or-later GPL-2.0-or-later MIT
PKG_LICENSE_FILES:=lgpl-2.1.txt gpl-2.0.txt lgpl-relicensing.txt

PKG_SOURCE:=userspace-rcu-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://lttng.org/files/urcu/
PKG_HASH:=92b9971bf3f1c443edd6c09e7bf5ff3b43531e778841f16377a812c8feeb3350
PKG_BUILD_DIR:=$(BUILD_DIR)/userspace-rcu-$(PKG_VERSION)

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1
PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk

define Package/liburcu
	SECTION:=libs
	CATEGORY:=Libraries
	TITLE:=User-space Read-Copy-Update library
	URL:=https://lttng.org/
	DEPENDS:=+libpthread @!TARGET_arc770 @!TARGET_archs38
endef

define Package/liburcu/description
	Userspace Read-Copy-Update library.
endef

define Build/InstallDev
	$(INSTALL_DIR)						$(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/urcu*		$(1)/usr/include/
	$(INSTALL_DIR)						$(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/liburcu*.{a,so*}	$(1)/usr/lib/
endef

define Package/liburcu/install
	$(INSTALL_DIR)					$(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/liburcu*.so.*	$(1)/usr/lib/
endef

$(eval $(call BuildPackage,liburcu))
