---
UID: NC:sensorscx.PFN_SENSORSCXDEVICEINITIALIZE
title: PFN_SENSORSCXDEVICEINITIALIZE (sensorscx.h)
description: Initializes the sensor in the class extension.
ms.assetid: cc62e248-377f-4018-89c5-618264a98a4e
ms.date: 10/19/2018
f1_keywords:
 - "sensorscx/*PFN_SENSORSCXDEVICEINITIALIZE"
req.header: sensorscx.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- UserDefined
api_location: 
- sensorscx.h
api_name: 
- PFN_SENSORSCXDEVICEINITIALIZE
product:
- Windows
targetos: Windows
ms.custom: RS5
---

# *PFN_SENSORSCXDEVICEINITIALIZE callback function

## -description

Initializes the sensor in the class extension.

## -prototype

```cpp
//Declaration

*PFN_SENSORSCXDEVICEINITIALIZE *PfnSensorscxdeviceinitialize; 

// Definition

NTSTATUS *PfnSensorscxdeviceinitialize 
(
	PSENSORSCX_DRIVER_GLOBALS DriverGlobals
	WDFDEVICE FxDevice
	PSENSOR_CONTROLLER_CONFIG pSensorConfig
)
{...}

```

## -parameters

### -param DriverGlobals

Global definitions for the driver.

### -param FxDevice

A WDFDEVICE handle to the framework device object that represents the sensor.

### -param pSensorConfig

A list of functions that the driver implements. 

## -returns

Returns NTSTATUS.
