---
title: "WinRUICleanup2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/30/2017"
ms.prod: "host-integration-server"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 620fb017-36f4-494d-83df-1def4d17366c
caps.latest.revision: 3
---
# WinRUICleanup
The **WinRUICleanup** function terminates and deregisters an application using Request Unit Interface (RUI) verbs from a Microsoft® Windows® logical unit application (LUA) implementation.  
  
## Syntax  
  
```  
  
BOOL WINAPI WinRUICleanup(void);  
```  
  
## Return Value  
 The return code specifies whether the deregistration was successful. If the value is not zero, the application was successfully deregistered. If the value is zero, the application was not deregistered.  
  
## Remarks  
 Use **WinRUICleanup** to indicate deregistration of a Windows LUA application from a Windows LUA implementation. This function can be used, for example, to free up resources allocated to the specific application.  
  
 If **WinRUICleanup** is called while LUs are in session ([RUI_TERM](../HIS2010/rui-term1.md) not issued), the cleanup code should issue an **RUI_TERM** close type ABEND for the application for all open sessions.  
  
## See Also  
 [RUI_TERM](../HIS2010/rui-term1.md)   
 [WinRUIStartup](../HIS2010/winruistartup2.md)