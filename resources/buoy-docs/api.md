---
title: "bluetoothkit API contracts"
summary: "Platform support, result semantics, and operational constraints for bluetoothkit."
category: "Reference"
order: 20
keywords: ["bluetoothkit", "BluetoothKit", "native", "discovery"]
symbols: ["BluetoothAdapterInfo", "BluetoothAdapters", "BluetoothAdapterDiscoverySupported", "BluetoothAdapterDiscoveryAvailable"]
related: ["index.md", "getting-started.md", "typed-api.md"]
---

# bluetoothkit API contracts

## Platform support

| Target | Backend | Availability probe |
| --- | --- | --- |
| Linux | BlueZ GetManagedObjects on system D-Bus | Loads GLib/GIO and connects to the system bus |
| Windows | SetupAPI radio interfaces | Probes SetupAPI and kernel32 |
| macOS | Unsupported | Returns False |

A successful probe does not establish that BlueZ is running or a radio exists. The Linux probe may block. Enumeration has a five-second D-Bus call timeout; perform it off the UI thread.

## Snapshot fields

`BluetoothAdapterInfo` contains read-only owned values. `Id` is the BlueZ object path on Linux or the device instance ID on Windows. Treat it as a backend-local observation rather than a portable identifier.

| Field | Linux | Windows |
| --- | --- | --- |
| Address | BlueZ address | None |
| Name | Optional BlueZ name | Optional SetupAPI text |
| Manufacturer | None | Optional SetupAPI text |
| IsPowered, IsDiscoverable, IsDiscovering | Optional BlueZ booleans | None |

`None` means the backend supplied no value. `Some("")` is a present empty string; an absent boolean does not mean False.

## Results and errors

An empty array means enumeration succeeded with no adapters. Missing services or native libraries, denied access, and native enumeration failures throw. Unsupported targets throw `UnsupportedOperationException` from enumeration. Importing or probing does not scan remote devices. This API neither pairs nor connects devices.

[Full typed reference](typed-api.md) · [Getting started](getting-started.md)
