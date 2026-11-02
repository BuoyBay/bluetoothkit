---
title: "bluetoothkit typed API"
summary: "Source-derived public signatures, properties, parameters, defaults, and return values."
category: "Reference"
order: 21
types: ["BluetoothAdapterInfo", "BluetoothKitLinuxBluetoothAdapter", "BluetoothKitLinuxNativeError", "BluetoothKitWindowsBluetoothRadio", "BluetoothKitWindowsNativeBluetoothDeviceInfo"]
dependencies: []
symbols: ["BluetoothAdapterInfo", "BluetoothKitLinuxBluetoothAdapter", "BluetoothKitLinuxNativeError", "BluetoothKitWindowsBluetoothRadio", "BluetoothKitWindowsNativeBluetoothDeviceInfo"]
related: ["api.md", "getting-started.md", "index.md"]
---

# bluetoothkit typed API

Generated from the package source declarations. Platform guards are shown where present; inherited members are documented on the base type. See the [API contracts](api.md) for behavior and limitations.

## BluetoothAdapterInfo

`Public Class BluetoothAdapterInfo`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Yes | No | — | — |
| `Address` | `Optional Of String` | Yes | No | — | — |
| `Name` | `Optional Of String` | Yes | No | — | — |
| `Manufacturer` | `Optional Of String` | Yes | No | — | — |
| `IsPowered` | `Optional Of Boolean` | Yes | No | — | — |
| `IsDiscoverable` | `Optional Of Boolean` | Yes | No | — | — |
| `IsDiscovering` | `Optional Of Boolean` | Yes | No | — | — |

### Constructor

`Public Sub Constructor(vId As String, vAddress As Optional Of String, vName As Optional Of String, vManufacturer As Optional Of String, vIsPowered As Optional Of Boolean, vIsDiscoverable As Optional Of Boolean, vIsDiscovering As Optional Of Boolean)`

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `vId` | `String` | `ByVal` | Required |
| `vAddress` | `Optional Of String` | `ByVal` | Required |
| `vName` | `Optional Of String` | `ByVal` | Required |
| `vManufacturer` | `Optional Of String` | `ByVal` | Required |
| `vIsPowered` | `Optional Of Boolean` | `ByVal` | Required |
| `vIsDiscoverable` | `Optional Of Boolean` | `ByVal` | Required |
| `vIsDiscovering` | `Optional Of Boolean` | `ByVal` | Required |

Returns: no value.

### BluetoothAdapterDiscoverySupported

`Public Function BluetoothAdapterDiscoverySupported() As Boolean`

Read-only compile-target backend test; no runtime I/O.

No parameters.

#### Returns

| Type |
| --- |
| `Boolean` |

### BluetoothAdapterDiscoveryAvailable

`Public Function BluetoothAdapterDiscoveryAvailable() As Boolean`

Read-only: Linux connects to system D-Bus and releases its reference (may block; use off UI thread); Windows probes libraries. Does not prove BlueZ or radio presence.

No parameters.

#### Returns

| Type |
| --- |
| `Boolean` |

### BluetoothAdapters

`Public Function BluetoothAdapters() As Array Of BluetoothAdapterInfo`

Read-only, may block on system D-Bus (5 second call timeout); use off UI thread. No radio scan, pairing or connection.

No parameters.

#### Returns

| Type |
| --- |
| `Array Of BluetoothAdapterInfo` |

## BluetoothKitLinuxBluetoothAdapter

`Public Class BluetoothKitLinuxBluetoothAdapter`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `ObjectPath` | `String` | No | No | — | — |
| `Address` | `String` | No | No | — | — |
| `Name` | `Optional Of String` | No | No | — | — |
| `Alias` | `Optional Of String` | No | No | — | — |
| `Powered` | `Optional Of Boolean` | No | No | — | — |
| `Discovering` | `Optional Of Boolean` | No | No | — | — |
| `Discoverable` | `Optional Of Boolean` | No | No | — | — |

## BluetoothKitLinuxNativeError

`Sequential Structure BluetoothKitLinuxNativeError`

### Fields

| Name | Type | Value / Default | Description |
| --- | --- | --- | --- |
| `Domain` | `UInt32` | — | — |
| `Code` | `Int32` | — | — |
| `Message` | `Ptr` | — | — |

### BluetoothKitLinuxIsSupported

`Public Function BluetoothKitLinuxIsSupported() As Boolean`

No parameters.

#### Returns

| Type |
| --- |
| `Boolean` |

### BluetoothKitLinuxIsAvailable

`Public Function BluetoothKitLinuxIsAvailable() As Boolean`

Native libraries only; this does not claim that system D-Bus or BlueZ is running.

No parameters.

#### Returns

| Type |
| --- |
| `Boolean` |

### BluetoothKitLinuxDecodeManagedObjects

`Public Function BluetoothKitLinuxDecodeManagedObjects(text As String) As Array Of BluetoothKitLinuxBluetoothAdapter`

Decode a recorded GetManagedObjects reply in GLib's GVariant text notation.

#### Parameters

| Name | Type | Passing | Default |
| --- | --- | --- | --- |
| `text` | `String` | `ByVal` | Required |

#### Returns

| Type |
| --- |
| `Array Of BluetoothKitLinuxBluetoothAdapter` |

### BluetoothKitLinuxAdapters

`Public Function BluetoothKitLinuxAdapters() As Array Of BluetoothKitLinuxBluetoothAdapter`

Query existing adapters once. Missing bus/service throws; zero adapters returns [].

No parameters.

#### Returns

| Type |
| --- |
| `Array Of BluetoothKitLinuxBluetoothAdapter` |

### BluetoothKitLinuxBusAvailable

`Public Function BluetoothKitLinuxBusAvailable() As Boolean`

No parameters.

#### Returns

| Type |
| --- |
| `Boolean` |

## BluetoothKitWindowsBluetoothRadio

`Public Class BluetoothKitWindowsBluetoothRadio`

### Properties

| Name | Type | Read-Only | Shared | Default | Description |
| --- | --- | --- | --- | --- | --- |
| `InstanceId` | `String` | No | No | — | — |
| `Name` | `Optional Of String` | No | No | — | — |
| `Manufacturer` | `Optional Of String` | No | No | — | — |
| `DeviceNode` | `Integer` | No | No | — | — |

## BluetoothKitWindowsNativeBluetoothDeviceInfo

`Sequential Structure BluetoothKitWindowsNativeBluetoothDeviceInfo`

### Fields

| Name | Type | Value / Default | Description |
| --- | --- | --- | --- |
| `Size` | `UInt32` | — | — |
| `GuidA` | `UInt32` | — | — |
| `GuidB` | `UInt32` | — | — |
| `GuidC` | `UInt32` | — | — |
| `GuidD` | `UInt32` | — | — |
| `DeviceNode` | `UInt32` | — | — |
| `Reserved` | `UInt64` | — | — |

### BluetoothKitWindowsIsSupported

`Public Function BluetoothKitWindowsIsSupported() As Boolean`

No parameters.

#### Returns

| Type |
| --- |
| `Boolean` |

### BluetoothKitWindowsIsAvailable

`Public Function BluetoothKitWindowsIsAvailable() As Boolean`

Library availability only; an installed backend can have no present hardware.

No parameters.

#### Returns

| Type |
| --- |
| `Boolean` |

### BluetoothKitWindowsPresentRadios

`Public Function BluetoothKitWindowsPresentRadios() As Array Of BluetoothKitWindowsBluetoothRadio`

One owned record per present Bluetooth radio device node; discovery can race hotplug.

No parameters.

#### Returns

| Type |
| --- |
| `Array Of BluetoothKitWindowsBluetoothRadio` |
