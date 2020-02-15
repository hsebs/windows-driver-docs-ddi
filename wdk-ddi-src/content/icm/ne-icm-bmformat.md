---
UID: NE:icm.BMFORMAT
title: BMFORMAT (icm.h)
description: The values of the BMFORMAT enumeration are used by WCS functions to indicate the format that particular bitmaps are in. This data type is extended from BMFORMAT that is available in versions of Windows released before Windows Vista.
old-location: print\bmformat.htm
tech.root: print
ms.assetid: 1c29bf1e-e785-48ab-aa2c-3665fd5c0ab0
ms.date: 04/20/2018
ms.keywords: "*PBMFORMAT, BMFORMAT, BMFORMAT enumeration [Print Devices], BM_10b_G3CH, BM_10b_Lab, BM_10b_RGB, BM_10b_XYZ, BM_10b_Yxy, BM_16b_G3CH, BM_16b_GRAY, BM_16b_Lab, BM_16b_RGB, BM_16b_XYZ, BM_16b_Yxy, BM_32b_scARGB, BM_32b_scRGB, BM_565RGB, BM_5CHANNEL, BM_6CHANNEL, BM_7CHANNEL, BM_8CHANNEL, BM_BGRTRIPLETS, BM_CMYKQUADS, BM_G3CHTRIPLETS, BM_GRAY, BM_KYMCQUADS, BM_LabTRIPLETS, BM_NAMED_INDEX, BM_R10G10B10A2, BM_R10G10B10A2_XR, BM_R16G16B16A16_FLOAT, BM_RGBTRIPLETS, BM_S2DOT13FIXED_scARGB, BM_S2DOT13FIXED_scRGB, BM_XYZTRIPLETS, BM_YxyTRIPLETS, BM_x555G3CH, BM_x555Lab, BM_x555RGB, BM_x555XYZ, BM_x555Yxy, BM_xBGRQUADS, BM_xG3CHQUADS, BM_xRGBQUADS, colorfnc_44898765-c0de-41ae-8036-b288ab45b3cb.xml, icm/BMFORMAT, icm/BM_10b_G3CH, icm/BM_10b_Lab, icm/BM_10b_RGB, icm/BM_10b_XYZ, icm/BM_10b_Yxy, icm/BM_16b_G3CH, icm/BM_16b_GRAY, icm/BM_16b_Lab, icm/BM_16b_RGB, icm/BM_16b_XYZ, icm/BM_16b_Yxy, icm/BM_32b_scARGB, icm/BM_32b_scRGB, icm/BM_565RGB, icm/BM_5CHANNEL, icm/BM_6CHANNEL, icm/BM_7CHANNEL, icm/BM_8CHANNEL, icm/BM_BGRTRIPLETS, icm/BM_CMYKQUADS, icm/BM_G3CHTRIPLETS, icm/BM_GRAY, icm/BM_KYMCQUADS, icm/BM_LabTRIPLETS, icm/BM_NAMED_INDEX, icm/BM_R10G10B10A2, icm/BM_R10G10B10A2_XR, icm/BM_R16G16B16A16_FLOAT, icm/BM_RGBTRIPLETS, icm/BM_S2DOT13FIXED_scARGB, icm/BM_S2DOT13FIXED_scRGB, icm/BM_XYZTRIPLETS, icm/BM_YxyTRIPLETS, icm/BM_x555G3CH, icm/BM_x555Lab, icm/BM_x555RGB, icm/BM_x555XYZ, icm/BM_x555Yxy, icm/BM_xBGRQUADS, icm/BM_xG3CHQUADS, icm/BM_xRGBQUADS, print.bmformat"
ms.topic: enum
req.header: icm.h
req.include-header: 
req.target-type: Windows
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	icm.h
api_name:
-	BMFORMAT
product:
- Windows
targetos: Windows
req.typenames: BMFORMAT
---

# BMFORMAT enumeration


## -description


The values of the BMFORMAT enumeration are used by WCS functions to indicate the format that particular bitmaps are in. This data type is extended from BMFORMAT that is available in versions of Windows released before Windows Vista.


## -enum-fields




### -field BM_x555RGB

16 bits per pixel. RGB color space. 5 bits per channel. The most significant bit is ignored.


### -field BM_x555XYZ

16 bits per pixel. Yxy color space. 5 bits per channel. The most significant bit is ignored.


### -field BM_x555Yxy

16 bits per pixel. Yxy color space. 5 bits per channel. The most significant bit is ignored.


### -field BM_x555Lab

BM_x555G3CH


### -field BM_x555G3CH

16 bits per pixel. G3CH color space. 5 bits per channel. The most significant bit is ignored.


### -field BM_RGBTRIPLETS

24 bits per pixel maximum. For three channel colors, such as red, green, and blue, the total size is 24 bits per pixel. For single channel colors, such as gray, the total size is 8 bits per pixel.


### -field BM_BGRTRIPLETS

24 bits per pixel maximum. For three channel colors, such as red, green, and blue, the total size is 24 bits per pixel. For single channel colors, such as gray, the total size is 8 bits per pixel.


### -field BM_XYZTRIPLETS

24 bits per pixel maximum. For three channel colors, such as red, green, and blue, the total size is 24 bits per pixel. For single channel colors, such as gray, the total size is 8 bits per pixel.


### -field BM_YxyTRIPLETS

24 bits per pixel maximum. For three channel, Y, x, and y values, the total size is 24 bits per pixel. For single channel gray scale, the total size is 8 bits per pixel.


### -field BM_LabTRIPLETS

24 bits per pixel maximum. For three channel, L, a, and b values, the total size is 24 bits per pixel. For single channel gray scale, the total size is 8 bits per pixel.


### -field BM_G3CHTRIPLETS

24 bits per pixel maximum. For three channel values, the total size is 24 bits per pixel. For single channel gray scale, the total size is 8 bits per pixel.


### -field BM_5CHANNEL

40 bits per pixel. 8 bits apiece are used for each channel.


### -field BM_6CHANNEL


### -field BM_7CHANNEL

56 bits per pixel. 8 bits apiece are used for each channel.


### -field BM_8CHANNEL

64 bits per pixel. 8 bits apiece are used for each channel.


### -field BM_GRAY

32 bits per pixel. Only the 8 bit gray-scale value is used.


### -field BM_xRGBQUADS

32 bits per pixel. 8 bits are used for each color channel. The most significant byte is ignored.


### -field BM_xBGRQUADS

32 bits per pixel. 8 bits are used for each color channel. The most significant byte is ignored.


### -field BM_xG3CHQUADS

32 bits per pixel. 8 bits are used for each color channel. The most significant byte is ignored.


### -field BM_KYMCQUADS

32 bits per pixel. 8 bits are used for each color channel.


### -field BM_CMYKQUADS

32 bits per pixel. 8 bits are used for each color channel.


### -field BM_10b_RGB

32 bits per pixel. 10 bits are used for each color channel. The 2 most significant bits are ignored. 


### -field BM_10b_XYZ

32 bits per pixel. 10 bits are used for each color channel. The 2 most significant bits are ignored.


### -field BM_10b_Yxy

32 bits per pixel. 10 bits are used for each color channel. The 2 most significant bits are ignored.


### -field BM_10b_Lab

32 bits per pixel. 10 bits are used for each color channel. The 2 most significant bits are ignored.


### -field BM_10b_G3CH

32 bits per pixel. 10 bits are used for each color channel. The 2 most significant bits are ignored.


### -field BM_NAMED_INDEX

32 bits per pixel. Named color indices. Index numbering begins at one. 


### -field BM_16b_RGB

64 bits per pixel. 16 bits are used for the gray-scale value. Each of the three color channels uses 16 bits.


### -field BM_16b_XYZ

64 bits per pixel. 16 bits are used for the gray-scale value. Each of the three color channels uses 16 bits.


### -field BM_16b_Yxy

64 bits per pixel. 16 bits are used for the gray-scale value. Each of the three color channels uses 16 bits.


### -field BM_16b_Lab

64 bits per pixel. 16 bits are used for the gray-scale value. Each of the three color channels uses 16 bits.


### -field BM_16b_G3CH

64 bits per pixel. 16 bits are used for the gray-scale value. Each of the three color channels uses 16 bits.


### -field BM_16b_GRAY

64 bits per pixel. 16 bits are used for the gray-scale value. All other bits are ignored.


### -field BM_565RGB

16 bits per pixel. 5 bits are used for red, 6 for green, and 5 for blue.


### -field BM_32b_scRGB

96 bits per pixel. 32 bits are used for each color channel, as defined by the IEEE 32-bit floating point standard.


### -field BM_32b_scARGB

128 bits per pixel. 32 bits are used for each color channel, as defined by the IEEE 32-bit floating point standard.


### -field BM_S2DOT13FIXED_scRGB

48 bits per pixel. Color data is stored as one 16-bit word per channel, with a fixed range of -4 to +4, inclusive. A signed format is used, with 1 bit for the sign, 2 bits for the integer portion, and 13 bits for the fractional portion.


### -field BM_S2DOT13FIXED_scARGB

64 bits per pixel. Color data is stored as one 16-bit word per channel, with a fixed range of -4 to +4, inclusive. A signed format is used, with 1 bit for the sign, 2 bits for the integer portion, and 13 bits for the fractional portion.


### -field BM_R10G10B10A2


### -field BM_R10G10B10A2_XR


### -field BM_R16G16B16A16_FLOAT

#endif // NTDDI_VERSION &gt;= NTDDI_WIN7


## -remarks



The last four values were added to the BMFORMAT enumeration beginning with Windows Vista.

The PBMFORMAT and LPBMFORMAT data types are defined as pointers to this enumeration:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef BMFORMAT *PBMFORMAT, *LPBMFORMAT;</pre>
</td>
</tr>
</table></span></div>


