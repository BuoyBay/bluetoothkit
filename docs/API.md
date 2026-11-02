# bluetoothkit

Import `bluetoothkit` (or `bluetoothkit.BluetoothKit`). This focused package owns `BluetoothAdapterDiscoverySupported()`, `BluetoothAdapterDiscoveryAvailable()` and `BluetoothAdapters() As Array Of BluetoothAdapterInfo`. It has no package, container, or external source dependency. Backend modules are implementation details and are non-public imports; their module-scope symbols are globally prefixed to avoid collisions.

Linux BlueZ GetManagedObjects over system D-Bus; Windows SetupAPI radio interface GUID. macOS is explicitly unsupported. Supported is a compile-target statement, not a runtime verification claim. Availability is a probe, not a promise that enumeration will succeed: Linux checks GLib/GIO, connects to the system bus and releases its reference; this may block, so use off the UI thread. Windows probes SetupAPI/kernel32 libraries. Neither proves a running BlueZ service or present radio.

Enumeration is read-only. Empty arrays mean successful enumeration with no results; missing services/libraries, denied access and native errors throw. Missing optional fields are None, present empty strings are Some(""). No absent numeric or powered state is fabricated as zero/False. Snapshot properties are read-only owned copies. Native IDs are observations in their backend namespace, not cross-platform stable identities or openable handles.

Adapter mapping: linuxbluetooth.Adapters / WinBluetooth.PresentRadios → BluetoothAdapters; BluetoothAdapter / BluetoothRadio → BluetoothAdapterInfo. ObjectPath / InstanceId map to Id. Linux Powered/Discoverable/Discovering become optional IsPowered/IsDiscoverable/IsDiscovering. Windows address and state remain None; manufacturer/name retain optional SetupAPI text. Alias is backend-only. Legacy entry modules are unchanged; no forwarding adapter is installed by this change.

Importing the package is supported across the declared compiler targets so callers can check capability predicates. A declared target does not imply that its native backend is implemented or available.

The operation inspects local adapters only, never remote devices. Linux may block on the system bus and has a 5-second GetManagedObjects timeout; use off the UI thread. Availability connects to the system bus but does not call BlueZ.
