include $(TOPDIR)/rules.mk

PKG_NAME:=gluon-autorestart
PKG_VERSION:=4
PKG_RELEASE:=$(GLUON_BRANCH)

PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

include $(TOPDIR)/../package/gluon.mk


define Package/gluon-autorestart
  SECTION:=gluon
  CATEGORY:=Gluon
  DEPENDS:=+micrond
  TITLE:=Restarts the router using micrond periodically
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile
	$(call GluonSrcDiet,./luasrc,$(PKG_BUILD_DIR)/luadest/)
endef

define Package/gluon-autorestart/install
	$(CP) ./files/* $(1)/
	$(CP) $(PKG_BUILD_DIR)/luadest/* $(1)/
endef

define Package/gluon-autorestart/postinst
#!/bin/sh
$(call GluonCheckSite,check_site.lua)
endef

$(eval $(call BuildPackage,gluon-autorestart))
