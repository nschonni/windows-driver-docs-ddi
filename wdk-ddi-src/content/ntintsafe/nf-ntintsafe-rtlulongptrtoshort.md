---
UID: NF:ntintsafe.RtlULongPtrToShort
title: RtlULongPtrToShort function (ntintsafe.h)
description: Converts a value of type ULONG_PTR to a value of type SHORT.
old-location: kernel\rtlulongptrtoshort.htm
tech.root: kernel
ms.assetid: 37C4A2B0-6FB4-431D-8FB2-0B13EE1F00F1
ms.date: 04/30/2018
ms.keywords: RtlULongPtrToShort, RtlULongPtrToShort function [Kernel-Mode Driver Architecture], kernel.rtlulongptrtoshort, ntintsafe/RtlULongPtrToShort
ms.topic: function
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntintsafe.h
api_name:
-	RtlULongPtrToShort
product:
- Windows
targetos: Windows
req.typenames: 
---

# RtlULongPtrToShort function


## -description


Converts a value of type <b>ULONG_PTR</b> to a value of type <b>SHORT</b>.


## -parameters




### -param ulOperand [in]

The value to be converted.


### -param psResult [out]

A pointer to the converted value. In the case where the conversion causes a truncation of the original value, the function returns STATUS_INTEGER_OVERFLOW and this parameter is not valid.


## -remarks



This is one of a set of inline functions designed to provide type conversions and perform validity checks with minimal impact on performance.

This function uses the following alternate name:

<ul>
<li>RtlULongPtrToUInt16
</li>
<li>RtlULongPtrToWord
</li>
<li>RtlDWordPtrToUShort
</li>
<li>RtlDWordPtrToUInt16
</li>
<li>RtlDWordPtrToWord
</li>
<li>RtlSIZETToUShort
</li>
<li>RtlSIZETToUInt16
</li>
<li>RtlSIZETToWord
</li>
</ul>


