# request cmake version required for zephyrs scripts
cmake_minimum_required(VERSION 3.13.1)

# create a new library
zephyr_library_named(acme-heater)

zephyr_library_sources(heater.c)

zephyr_library_sources_ifdef(CONFIG_SHELL heater_shell.c)
zephyr_library_sources_ifdef(CONFIG_ACME_SUBSYS_HEATER_MQTT_RPC heater_mqttrpc.c)
zephyr_library_sources_ifdef(CONFIG_ACME_SUBSYS_HEATER_SCOPE heater_scope.c)


