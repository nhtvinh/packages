#
# Copyright (C) 2009-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=make-dfsg
PKG_VERSION:=3.81

PKG_SOURCE_NAME:=$(PKG_NAME)-$(PKG_VERSION).orig
PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION).orig.tar.gz
PKG_SOURCE_URL:=https://ftp.iitm.ac.in/ubuntu/pool/main/m/make-dfsg/
PKG_MD5SUM:=7c93b1ab4680eb21c2c13f4f47741e2d

include $(INCLUDE_DIR)/package.mk

define Package/gnu-make
  SECTION:=devel
  CATEGORY:=Development
  TITLE:=GNU Make for development
  URL:=https://www.gnu.org/software/make/
endef

define Package/gnu-make/description
 A tool to help developer to build a complicated project.
endef

define Build/Patch
	$(CP) -r $(BUILD_DIR)/$(PKG_SOURCE_NAME)/* $(PKG_BUILD_DIR)/
	$(RM) -r $(BUILD_DIR)/$(PKG_SOURCE_NAME)
	 $(call Build/Patch/Default)
endef

define Package/gnu-make/install
	$(INSTALL_DIR) $(1)/usr/bin 
	$(CP) $(PKG_BUILD_DIR)/make $(1)/usr/bin
endef

$(eval $(call BuildPackage,gnu-make))
