---
UID: NC:pcivirt.SRIOV_WRITE_CONFIG
title: SRIOV_WRITE_CONFIG (pcivirt.h)
description: Writes configuration data to a PCI Express SR-IOV Virtual Function (VF).
old-location: pci\sriov_write_config.htm
tech.root: PCI
ms.assetid: 323c8150-ef58-42a4-8c8b-77081ecb64b3
ms.date: 02/24/2018
ms.keywords: "*PSRIOV_WRITE_CONFIG, *PSRIOV_WRITE_CONFIG callback function pointer [Buses], PCI.sriov_write_config, SRIOV_WRITE_CONFIG, SriovWriteConfig, SriovWriteConfig callback function [Buses], pcivirt/SriovWriteConfig"
f1_keywords:
 - "pcivirt/*PSRIOV_WRITE_CONFIG"
req.header: pcivirt.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Pcivirt.h
api_name:
- PSRIOV_WRITE_CONFIG
product:
- Windows
targetos: Windows
req.typenames: PARCLASS_INFORMATION, *PPARCLASS_INFORMATION
---

# SRIOV_WRITE_CONFIG callback


## -description


Writes configuration data to a PCI Express SR-IOV Virtual Function (VF).


## -prototype


```cpp
SRIOV_WRITE_CONFIG SriovWriteConfig;

NTSTATUS SriovWriteConfig(
  _In_       PVOID  Context,
  _In_ const VOID   *Data,
  _In_       USHORT VfIndex,
  _In_       ULONG  Offset,
  _In_       ULONG  Length
)
{ ... }

typedef SRIOV_WRITE_CONFIG *PSRIOV_WRITE_CONFIG;
```


## -parameters




### -param Context [in]

A pointer to a driver-defined context.




### -param Data [in]

A pointer to buffer that contains the data to be written to the configuration space.


### -param VfIndex [in]

A zero-based index of the VF to which this write operation applies.


### -param Offset [in]

An offset in bytes to the start of the VF’s configuration space where the write begins.


### -param Length [in]

The length, in bytes, of the data to write to the configuration space.


## -returns




Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code.




## -remarks



This callback function is implemented by the physical function (PF) driver. It is invoked  when the system wants to write to the configuration space of a specific virtual function.

The PF driver registers its implementation by setting the <b>WriteVfConfig</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ns-pcivirt-_sriov_device_interface_standard">SRIOV_DEVICE_INTERFACE_STANDARD</a>, configuring a <a href="..\wdfqueryinterface\ns-wdfqueryinterface-_wdf_query_interface_config.md">WDF_QUERY_INTERFACE_CONFIG</a> structure, and calling <a href="..\wdfqueryinterface\nf-wdfqueryinterface-wdfdeviceaddqueryinterface.md">WdfDeviceAddQueryInterface</a>.



