include $(TOPDIR)/rules.mk

PKG_NAME:=ampr-ripd
PKG_VERSION:=2.4
PKG_RELEASE:=1
PKG_SOURCE_URL:=http://www.yo2loj.ro/hamprojects
PKG_MD5SUM:=3753e634aa1154ebba290d0cd4055891

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tgz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)    
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Routing and Redirection
	TITLE:=Routing daemon for the AMPR network
	MAINTAINER:=Bill Hill <bugs@wbh.org>
endef

define Package/$(PKG_NAME)/description
	Routing daemon written in C similar to Hessu's rip44d including optional resending of RIPv2 broadcasts for router injection.
endef

CONFIGURE_VARS+= \
	CC="$(TOOLCHAIN_DIR)/bin/$(TARGET_CC)"

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(CP) $(PKG_BUILD_DIR)/$(PKG_NAME) $(1)/usr/sbin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
