include $(TOPDIR)/rules.mk

PKG_NAME:=amprd
PKG_VERSION:=1.6
PKG_RELEASE:=1
PKG_SOURCE_URL:=http://www.yo2loj.ro/hamprojects
PKG_MD5SUM:=63fc67c4af32a65976e0680310eaea7a

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tgz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)    
	SECTION:=net
	CATEGORY:=Network
	TITLE:=$(PKG_NAME)
	MAINTAINER:=Bill Hill <bugs@wbh.org>
endef

define Package/$(PKG_NAME)/description
	A user-space IPIP encapsulation daemon with automatic RIPv2 multicast processing and multiple tunnel support for the ampr network.
endef

CONFIGURE_VARS+= \
	CC="$(TOOLCHAIN_DIR)/bin/$(TARGET_CC)"

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/sbin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
