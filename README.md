# List local Bluetooth devices

Import `bluetoothkit` (or `bluetoothkit.BluetoothKit`). This focused package owns `BluetoothAdapterDiscoverySupported()`, `BluetoothAdapterDiscoveryAvailable()` and `BluetoothAdapters() As Array Of BluetoothAdapterInfo`. It lists the host's Bluetooth radios as local devices. It does not scan nearby peripherals, and it does not pair or connect. It has no package, container, or external source dependency. Backend modules are implementation details and are non-public imports; their module-scope symbols are globally prefixed to avoid collisions.

Enumeration is read-only. Empty arrays mean successful enumeration with no results; missing services/libraries, denied access and native errors throw. Missing optional fields are None, present empty strings are Some(""). No absent numeric or powered state is fabricated as zero/False. Snapshot properties are read-only owned copies. Native IDs are observations in their backend namespace, not cross-platform stable identities or openable handles.

## Install

From a Buoy consumer project with BPM installed:

```sh
bpm add bluetoothkit --git https://github.com/BuoyBay/bluetoothkit.git --rev refs/heads/main
```

BPM records the resolved commit in its lockfile. Keep that lockfile with the
consumer project for reproducible installs.

## API entrypoints

- `BluetoothAdapterDiscoverySupported()`
- `BluetoothAdapterDiscoveryAvailable()`
- `BluetoothAdapters() As Array Of BluetoothAdapterInfo`

## Platform and scope

Uses Linux BlueZ over D-Bus and Windows SetupAPI. macOS is unsupported. Enumeration is read-only and service availability is separate from hardware presence.

## Build from source

With the native `build-packages` driver from [devtools](https://github.com/BuoyBay/devtools)
on your `PATH`, run from this checkout:

```sh
build-packages --root "$PWD" --compile-consumer bluetoothkit
```

The driver checks source targets and compiles an import consumer. See the
[API guide](docs/API.md) for behavior, limits and any host prerequisites.

## Local Buoy setup

On your own machine, install Buoy and run:

```sh
buoy ai init --both
```


## Contributing

[Contributing](CONTRIBUTING.md) · [License](LICENSE)
