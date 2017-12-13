---
title: "WinCPICIsBlocking2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/30/2017"
ms.prod: "host-integration-server"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 077fcd44-1fd4-42a3-b6c6-1bb3720c5567
caps.latest.revision: 3
---
# WinCPICIsBlocking
The **WinCPICIsBlocking** function determines if a task is executing while waiting for a previous blocking call to finish.  
  
## Syntax  
  
```  
  
BOOL WINAPI WinCPICIsBlocking(void);  
```  
  
## Return Value  
 The return value specifies the outcome of the function. If the value is not zero, there is an outstanding blocking call awaiting completion. A value of zero indicates the absence of an outstanding blocking call.  
  
## Remarks  
 This call does not infer any information about a particular conversation; it is only intended to provide help to an application written to use the CM_BLOCKING characteristic of [Set_Processing_Mode](../HIS2010/set-processing-mode-cpi-c-1.md). **WinCPICIsBlocking** serves the same purpose as **InSendMessage** in the Microsoft® Windows® API. Legacy applications targeted at Windows version 3.*x* that support multiple conversations must specify CM_NONBLOCKING in **Set_Processing_Mode** so they can support multiple outstanding operations simultaneously. Applications are still limited to one outstanding operation per conversation in all environments.  
  
 Although a call issued on a blocking function appears to an application as though it blocks, the Windows CPI-C dynamic-link library (DLL) has to relinquish the processor to allow other applications to run. This means that it is possible for the application that issued the blocking call to be re-entered, depending on the messages it receives. In this instance, **WinCPICIsBlocking** can be used to determine whether the application task currently has been re-entered while waiting for an outstanding blocking call to finish. Note that Windows CPI-C prohibits more than one outstanding blocking call per thread.  
  
## See Also  
 [Specify_Windows_Handle (CPI-C)](../HIS2010/specify-windows-handle-cpi-c-1.md)   
 [WinCPICSetBlockingHook](../HIS2010/wincpicsetblockinghook1.md)   
 [WinCPICUnhookBlockingHook](../HIS2010/wincpicunhookblockinghook1.md)