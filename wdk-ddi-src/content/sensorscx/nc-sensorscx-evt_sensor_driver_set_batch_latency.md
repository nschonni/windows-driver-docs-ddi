---
UID: NC:sensorscx.EVT_SENSOR_DRIVER_SET_BATCH_LATENCY
title: EVT_SENSOR_DRIVER_SET_BATCH_LATENCY
author: windows-driver-content
description: This callback function sets the batch latency for a specified sensor.
old-location: sensors\evtsensorsetbatchlatency.htm
old-project: sensors
ms.assetid: 11C90E96-2A5D-4CD8-AC96-115CFEF3CE12
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: EVT_SENSOR_DRIVER_SET_BATCH_LATENCY, EvtSensorSetBatchLatency, EvtSensorSetBatchLatency callback function [Sensor Devices], sensors.evtsensorsetbatchlatency, sensorscx/EvtSensorSetBatchLatency
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sensorscx.h
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
req.irql: "_requires_same_"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	SensorsCx.h
apiname:
-	EvtSensorSetBatchLatency
product: Windows
targetos: Windows
req.typenames: SensorConnectionType
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_SET_BATCH_LATENCY callback


## -description


This callback function sets the batch latency for a specified sensor.


## -prototype


````
NTSTATUS EvtSensorSetBatchLatency(
  _In_ SENSOROBJECT Sensor,
  _In_ ULONG        BatchLatencyMs
);
````


## -parameters




### -param Sensor [in]

A reference to a sensor object.


### -param BatchLatencyMs [in]

The batch latency, expressed in milliseconds.


## -returns



This function returns STATUS_SUCCESS when completed successfully.

<b>Note</b> The class extension (CX) only uses the NT_SUCCESS macro to determine if the call to the driver’s Evt function was successful, but does not take any action if the function failed or does not return STATUS_SUCCESS.




## -remarks



The driver can set the batch latency to a value that is less than or equal to <i>BatchLatencyMs</i>, depending on buffer availability. For information about the sensor properties that a data batching sensor driver must report, see <a href="https://msdn.microsoft.com/library/windows/hardware/dn957018">Common sensor properties</a>.

It is important to note that there is no change implied to sensor data delivery methods and events, due to data batching.  When data batching latency expires, the driver will call <a href="..\sensorscx\nf-sensorscx-sensorscxsensordataready.md">SensorsCxSensorDataReady</a> repeatedly to deliver all the buffered data samples, one at a time. The data samples are sent, along with the timestamp information in their <b>PKEY_SensorData_Timestamp</b>  data fields. The timestamp information (of data type VT_FILETIME) shows the time  at which a sample was taken.

For more information about the VT_FILETIME data type, see <a href="http://go.microsoft.com/fwlink/p/?linkid=313395">MSDN PROPVARIANT structure</a>.




## -see-also

<a href="http://go.microsoft.com/fwlink/p/?linkid=313395">MSDN PROPVARIANT structure</a>



<a href="..\sensorscx\nf-sensorscx-sensorscxsensordataready.md">SensorsCxSensorDataReady</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20EVT_SENSOR_DRIVER_SET_BATCH_LATENCY callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
