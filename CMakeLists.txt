# nrfxlib's zephyr/module.yml declares cmake-ext: True but provides no cmake
# extension files, so NRFXLIB_DIR is never set by nrfxlib itself. sdk-nrf's
# nrf_security builds paths as ${NRFXLIB_DIR}/... which resolve to /... when
# NRFXLIB_DIR is empty. Set it here from the variable Zephyr always provides
# for any west module that is in the workspace.
if(DEFINED ZEPHYR_NRFXLIB_MODULE_DIR)
  set(NRFXLIB_DIR "${ZEPHYR_NRFXLIB_MODULE_DIR}" CACHE PATH
      "nrfxlib base directory (set from ZEPHYR_NRFXLIB_MODULE_DIR)" FORCE)
endif()
