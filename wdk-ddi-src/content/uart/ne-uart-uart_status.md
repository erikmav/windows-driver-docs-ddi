---
UID: NE:uart.UART_STATUS
title: UART_STATUS (uart.h)
description: Defines values for the status of a UART operation.
tech.root: serports
ms.date: 10/19/2018
keywords: ["UART_STATUS enumeration"]
ms.keywords: UART_STATUS, UART_STATUS, *PUART_STATUS,
req.header: uart.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: UART_STATUS, *PUART_STATUS
targetos: Windows
f1_keywords:
 - PUART_STATUS
 - uart/PUART_STATUS
 - UART_STATUS
 - uart/UART_STATUS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - uart.h
api_name:
 - PUART_STATUS
 - UART_STATUS
---

# UART_STATUS enumeration


## -description

Defines values for the status of a UART operation.

## -enum-fields

### -field UartSuccess

The operation was successful, for example if data was available.

### -field UartNoData

No data is available, but not due to an error condition.

### -field UartError

A UART error such as overrun, parity, framing, etc.

### -field UartNotReady

The device is not ready.

## -remarks

## -see-also

