---
title: "Getting started with bluetoothkit"
summary: "Import bluetoothkit, check platform availability, and handle results and failures."
category: "Guide"
order: 10
keywords: ["bluetoothkit", "BluetoothKit", "native", "discovery"]
symbols: ["BluetoothAdapterInfo", "BluetoothAdapters", "BluetoothAdapterDiscoverySupported", "BluetoothAdapterDiscoveryAvailable"]
related: ["index.md", "api.md", "typed-api.md"]
---

# Getting started

Install `bluetoothkit` into your project’s packages directory with your package workflow, then import `bluetoothkit`. Use the BluetoothKit facade instead of importing platform backend modules.

Check `BluetoothAdapterDiscoverySupported()` before offering adapter discovery. If supported, call `BluetoothAdapterDiscoveryAvailable()` off the UI thread, then call `BluetoothAdapters()` inside your application’s exception handling. Present the resulting `Array Of BluetoothAdapterInfo` as a snapshot and refresh explicitly when needed.

## Handling availability

A Supported predicate describes the compile target. An Available predicate probes runtime prerequisites; it does not guarantee that the next operation will succeed. Preserve the distinction between successful empty results and an exception. Consult the [API contracts](api.md) for supported platforms, blocking behavior, and lifecycle requirements.

The [typed reference](typed-api.md) lists argument types, defaults, read-only properties, and return values. It also includes declarations from internal backend source modules; applications should use the facade entry points described here.
