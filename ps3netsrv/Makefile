#
# Copyright (C) 2012-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=ps3netsrv
PKG_VERSION:=20170310
PKG_GIT_COMMIT:=a61f9354a2d122e92f9336ac6f110d911ad0e629
PKG_RELEASE:=1

PKG_SOURCE:=aldostools-$(PKG_NAME)-$(PKG_VERSION)-$(PKG_GIT_COMMIT).tar.gz
PKG_SOURCE_URL:=https://archive.midnightchannel.net/SonyPS/PS3/Source%20Code/
PKG_HASH:=a73bf3c378a0eed644aafda1493c0a9c8a013c2b5334daa3add6b2a229d14745
PKG_INSTALL:=1

PKG_MAINTAINER:=zefie <zefie@zefie.net>
PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk

define Package/ps3netsrv
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=File Transfer
  TITLE:=PS3 Game Server
  URL:=https://archive.midnightchannel.net/SonyPS/PS3/
  DEPENDS:=+libpthread +libstdcpp
endef

define Package/ps3netsrv/description
ps3netsrv allows you to stream games and ISOs over the network to your CFW PlayStation(R) 3 system.
This may be useful if you have a modified PS3, and your router has storage options.
endef

define Build/Install
	# Do nothing
endef

define Package/ps3netsrv/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ps3netsrv $(1)/usr/bin

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/ps3netsrv.init $(1)/etc/init.d/ps3netsrv

	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./files/ps3netsrv.config $(1)/etc/config/ps3netsrv
endef

$(eval $(call BuildPackage,ps3netsrv))
