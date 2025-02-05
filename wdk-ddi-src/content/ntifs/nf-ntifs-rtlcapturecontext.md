---
UID: NF:ntifs.RtlCaptureContext
title: RtlCaptureContext function (ntifs.h)
description: The RtlCaptureContext function retrieves a context record in the context of the caller.
old-location: ifsk\rtlcapturecontext.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["RtlCaptureContext function"]
ms.keywords: RtlCaptureContext, RtlCaptureContext function [Installable File System Drivers], ifsk.rtlcapturecontext, ntifs/RtlCaptureContext, rtlref_efe764ec-89fb-43bc-945d-7fee4594c284.xml
req.header: ntifs.h
req.include-header: Fltkernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
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
req.lib: NtosKrnl.lib; OneCoreUAP.lib on Windows 10
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - RtlCaptureContext
 - ntifs/RtlCaptureContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtDll.dll
 - NtosKrnl.exe
 - API-MS-Win-Core-RTLSupport-l1-1-0.dll
 - API-MS-Win-Core-RTLSupport-l1-2-0.dll
api_name:
 - RtlCaptureContext
---

# RtlCaptureContext function


## -description

The <b>RtlCaptureContext </b>function retrieves a context record in the context of the caller.

## -parameters

### -param ContextRecord [out]


A pointer to a <a href="/windows/win32/api/winnt/ns-winnt-arm64_nt_context">CONTEXT</a> structure.

## -returns

This function does not return a value.

## -remarks

The <i>ContextRecord</i> that is captured contains processor-specific register data.  

For kernel-mode code, the CONTEXT structure is defined in <i>Ntddk.h</i>. For more information, see the <a href="/windows/win32/api/winnt/ns-winnt-arm64_nt_context">CONTEXT</a> Structure topic in the SDK documentation.

## -see-also

<a href="/windows/win32/api/winnt/ns-winnt-arm64_nt_context">CONTEXT</a>
