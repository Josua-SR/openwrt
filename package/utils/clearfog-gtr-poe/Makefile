#
# Copyright (C) 2023 Josua Mayer <josua@solid-run.com>
#

include $(TOPDIR)/rules.mk

PKG_NAME:=clearfog-gtr-poe
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=https://github.com/SolidRun/ti-poe.git
PKG_SOURCE_DATE:=2021-06-01
PKG_SOURCE_VERSION:=8dfc35df52cb606c972cbb06d464148079a92b6b
PKG_MIRROR_HASH:=cd2112ae03ae7fb644350ef86aafbbc51b2c671af8283a37cc980d53a6c36240

PKG_LICENSE:=BSD-3-Clause

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/meson.mk

define Package/clearfog-gtr-poe
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Clearfog GTR PoE Controller
  BUILD_DEVICES:=solidrun_clearfog-gtr-l8
  BUILD_SUBTARGET:=cortexa9
endef

define Package/clearfog-gtr-poe/install
	$(INSTALL_DIR) $(1)/usr/sbin $(1)/etc/init.d
	$(INSTALL_BIN) ./files/clearfog-gtr-poe.init $(1)/etc/init.d/clearfog-gtr-poe
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/openwrt-build/tps2388-init $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,clearfog-gtr-poe))
