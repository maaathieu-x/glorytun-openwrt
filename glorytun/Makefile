include $(TOPDIR)/rules.mk

PKG_NAME:=glorytun
PKG_VERSION:=0.3.4
PKG_RELEASE:=0
PKG_SOURCE:=glorytun-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/angt/glorytun/releases/download/v$(PKG_VERSION)
PKG_HASH:=1f6bd01731e40e51d634555bcaab90deafcc738e55722a599186533793c1315b
PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/glorytun
SECTION:=net
CATEGORY:=Network
DEPENDS:=+kmod-tun +libsodium +librt
TITLE:=Glorytun
URL:=https://github.com/angt/glorytun
SUBMENU:=VPN
endef

define Package/glorytun/description
Glorytun is a vpn designed to improve your internet connectivity:
 - Fast and highly secure.
 - Multipath and active failover.
 - Traffic shaping.
 - Path MTU discovery without ICMP.
endef

define Package/glorytun/conffiles
/etc/config/glorytun
endef

define Package/glorytun/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/glorytun $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) init $(1)/etc/init.d/glorytun
	$(INSTALL_DIR) $(1)/etc/config
	touch $(1)/etc/config/glorytun
endef

$(eval $(call BuildPackage,glorytun))
