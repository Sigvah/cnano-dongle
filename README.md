This is my experimental branch using low-latency split BLE to connect the dongle to my dual cnano.

It runs **stock ZMK** (`zmkfirmware/zmk` main) with no ESB modules or forks. The low-latency split connection is configured purely via Kconfig, following [zmkfirmware/zmk#3381](https://github.com/zmkfirmware/zmk/issues/3381): the dongle (central) enables the Zephyr controller low-latency features, and each half (peripheral) drives the fast connection parameters (MIN/MAX interval = 3 for multi-peripheral stability, with auto connection-parameter update). Latency is a bit worse than the ESB setup, but it's good enough for general trackball use and keeps battery status / display working over standard BLE.

For the ESB version, use the ESB branch. For the old bluetooth version, use the bluetooth branch.
