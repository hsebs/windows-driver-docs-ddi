---
UID: NF:ntintsafe.RtlLongPtrToIntPtr
title: RtlLongPtrToIntPtr function (ntintsafe.h)
description: Converts a value of type LONG_PTR to a value of type INT_PTR.
old-location: kernel\rtllongptrtointptr.htm
tech.root: kernel
ms.assetid: 14E208AA-E22C-4D7D-9261-15C38E65951F
ms.date: 04/30/2018
ms.keywords: RtlLongPtrToIntPtr, RtlLongPtrToIntPtr function [Kernel-Mode Driver Architecture], kernel.rtllongptrtointptr, ntintsafe/RtlLongPtrToIntPtr
f1_keywords:
 - "ntintsafe/RtlLongPtrToIntPtr"
req.header: ntintsafe.h
req.include-header: 
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntintsafe.h
api_name:
- RtlLongPtrToIntPtr
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlLongPtrToIntPtr function


## -description


Converts a value of type <b>LONG_PTR</b> to a value of type <b>INT_PTR</b>.


## -parameters




### -param lOperand [in]

The value to be converted.


### -param piResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>
RtlSSIZETToIntPtr
</li>
</ul>


