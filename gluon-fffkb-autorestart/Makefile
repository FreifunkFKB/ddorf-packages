include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-fffkb-autorestart
PKG_VERSION:=3

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(INCLUDE_DIR)/package.mk

define Package/gluon-fffkb-autorestart
  SECTION:=gluon
  CATEGORY:=Gluon
  TITLE:=Support for connecting batman-adv meshes via tunneltigger/l2tpv3 pseudowire
  DEPENDS:=+micrond
endef

define Package/gluon-fffkb-autorestart/description
	Gluon community wifi mesh firmware framework: tunneldigger support
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/gluon-fffkb-autorestart/install
	$(CP) ./files/* $(1)/
endef

define Package/gluon-fffkb-autorestart/postinst
#!/bin/sh
$(call GluonCheckSite,check_site.lua)
endef

$(eval $(call BuildPackage,gluon-fffkb-autorestart))
