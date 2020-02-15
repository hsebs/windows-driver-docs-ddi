---
UID: NF:icm.WcsGetUsePerUserProfiles
title: WcsGetUsePerUserProfiles function (icm.h)
description: The WcsGetUsePerUserProfiles function determines whether the user has chosen to use a per-user profile association list for the specified device.
old-location: print\wcsgetuseperuserprofiles.htm
tech.root: print
ms.assetid: 6a970bec-c773-498e-b93a-2bd9f625e194
ms.date: 04/20/2018
ms.keywords: WcsGetUsePerUserProfiles, WcsGetUsePerUserProfiles function [Print Devices], colorfnc_b80783e5-17c0-4069-90ba-71ea82a2d7d5.xml, icm/WcsGetUsePerUserProfiles, print.wcsgetuseperuserprofiles
ms.topic: function
req.header: icm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Mscms.lib
req.dll: Mscms.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Mscms.dll
api_name:
-	WcsGetUsePerUserProfiles
product:
- Windows
targetos: Windows
req.typenames: 
---

# WcsGetUsePerUserProfiles function

## -description

The <code>WcsGetUsePerUserProfiles</code> function determines whether the user has chosen to use a per-user profile association list for the specified device.

## -parameters

### -param pDeviceName [in]

A pointer to a string that contains the friendly name of the device.

### -param dwDeviceClass [in]

A flag value that specifies the class of the device. This parameter must take one of the following values:

#### CLASS_MONITOR

Specifies a display device.

#### CLASS_PRINTER

Specifies a printer.

#### CLASS_SCANNER

Specifies an image capture device.

### -param pUsePerUserProfiles [out]

A pointer to a location to receive a Boolean value that is **TRUE** if the user has chosen to use a per-user profile association list for the specified device; otherwise **FALSE**.

## -remarks

This function will fail if the device pointed to by *pDeviceName* is not of the class specified by *dwDeviceClass*.

This function is executable in Least-Privileged User Account (LUA) context.

## -see-also

[WcsSetUsePerUserProfiles](nf-icm-wcssetuseperuserprofiles.md)
