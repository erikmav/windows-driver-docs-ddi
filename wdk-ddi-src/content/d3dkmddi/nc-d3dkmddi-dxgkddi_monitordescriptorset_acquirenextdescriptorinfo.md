---
UID: NC:d3dkmddi.DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO
title: DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO (d3dkmddi.h)
description: The pfnAcquireNextDescriptorInfo function returns the next descriptor in a monitor descriptor set, given the current descriptor.
old-location: display\dxgk_monitordescriptorset_interface_pfnacquirenextdescriptorinfo.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO callback function"]
ms.keywords: DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO, DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO callback, VidPnFunctions_ae273fb1-032c-4d22-86ef-849a4650c82e.xml, d3dkmddi/pfnAcquireNextDescriptorInfo, display.dxgk_monitordescriptorset_interface_pfnacquirenextdescriptorinfo, pfnAcquireNextDescriptorInfo, pfnAcquireNextDescriptorInfo callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO
 - d3dkmddi/DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO
product:
 - Windows
---

# DXGKDDI_MONITORDESCRIPTORSET_ACQUIRENEXTDESCRIPTORINFO callback function


## -description

The <b>pfnAcquireNextDescriptorInfo</b> function returns the next descriptor in a monitor descriptor set, given the current descriptor.

## -parameters

### -param hMonitorDescriptorSet [in]

A handle to a monitor descriptor set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitor_getmonitordescriptorset">pfnGetMonitorDescriptorSet</a> function of the <a href="/windows-hardware/drivers/ddi/index">Monitor interface</a>.

### -param pMonitorDescriptorInfo [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_descriptor">D3DKMDT_MONITOR_DESCRIPTOR</a> structure that is the current descriptor. The display miniport driver previously obtained this pointer by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo">pfnAcquireFirstDescriptorInfo</a> or <b>pfnAcquireNextDescriptorInfo</b>.

### -param ppNextMonitorDescriptorInfo [out]

A pointer to a variable that receives a pointer to a <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_d3dkmdt_monitor_descriptor">D3DKMDT_MONITOR_DESCRIPTOR</a> structure. The structure is the next descriptor in the set.

## -returns

The <b>pfnAcquireNextDescriptorInfo</b> function returns one of the following values.

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function successfully returned the next descriptor in the set.|
|STATUS_GRAPHICS_NO_MORE_ELEMENTS_IN_DATASET|The function succeeded, but there were no more descriptors in the set.|
|STATUS_INVALID_PARAMETER|An invalid parameter was supplied.|
|STATUS_INVALID_MONITOR_DESCRIPTOR|The descriptor supplied in pMonitorDescriptorInfo was invalid.|
|STATUS_GRAPHICS_INVALID_MONITOR_DESCRIPTORSET|The handle supplied in hMonitorDescriptorSet was invalid.|

## -remarks

When you have finished using the D3DKMDT_MONITOR_DESCRIPTOR structure, you must release the structure by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_releasedescriptorinfo">pfnReleaseDescriptorInfo</a>.

You can obtain all the descriptors in a monitor descriptor set by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_monitordescriptorset_acquirefirstdescriptorinfo">pfnAcquireFirstDescriptorInfo</a> and then making a sequence of calls to <b>pfnAcquireNextDescriptorInfo</b>.

