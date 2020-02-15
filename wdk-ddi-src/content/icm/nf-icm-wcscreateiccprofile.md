---
UID: NF:icm.WcsCreateIccProfile
title: WcsCreateIccProfile function (icm.h)
description: The WcsCreateIccProfile function converts a WCS profile into an ICC profile.
old-location: print\wcscreateiccprofile.htm
tech.root: print
ms.assetid: fbe37d6c-9b91-46d8-9d29-1de3ef542c19
ms.date: 04/20/2018
ms.keywords: WcsCreateIccProfile, WcsCreateIccProfile function [Print Devices], colorfnc_cb099d17-1109-4cb5-bbdc-76f1df13c60b.xml, icm/WcsCreateIccProfile, print.wcscreateiccprofile
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
-	WcsCreateIccProfile
product:
- Windows
targetos: Windows
req.typenames: 
---

# WcsCreateIccProfile function


## -description


The <code>WcsCreateIccProfile</code> function converts a WCS profile into an ICC profile.


## -parameters




### -param hWcsProfile [in]

A handle to the WCS color profile to transform. See Remarks.


### -param dwOptions [in]

A flag value that specifies the profile conversion options. This parameter must take the following value:





#### PREFER_WCS_PROFILES

Specifies that when WCS encounters an ICC profile, it should extract and use the WCS profiles that are contained in <b>WcsProfilesTag</b>.


## -remarks



The WCS profile that is to be translated must be a Device Model Profile (DMP) in combination with a Color Appearance Model Profile (CAMP) and a Gamut Map Model Profile (GMMP).



