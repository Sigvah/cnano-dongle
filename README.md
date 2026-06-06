This is my experimental branch using low-latency split BLE to connect the dongle to my dual cnano.

It runs stock ZMK via [carrefinho/zmk `sci-dev`](https://github.com/carrefinho/zmk/tree/sci-dev) (no ESB modules) with tuned split connection parameters: 1-interval / high-latency on the dongle (central) and both halves (peripheral). Latency is a bit worse than the ESB setup, but it's still good enough for general trackball use and keeps battery status / display working over standard BLE.

For the ESB version, use the ESB branch. For the old bluetooth version, use the bluetooth branch.
