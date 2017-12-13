---
title: "SNAModemInitialize1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/30/2017"
ms.prod: "host-integration-server"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0a4ef333-5956-4229-88c8-77d9ad146028
caps.latest.revision: 3
---
# SNAModemInitialize
The **SNAModemInitialize** function should be called once per link service process at initialization. This function initializes the communication path to the SNA Modem application. The ideal place to call this function is in the **SNALinkInitialize** function.  
  
## Syntax  
  
```  
  
void SNAModemInitialize();  
  
```  
  
## See Also  
 [SNALinkInitialize](../HIS2010/snalinkinitialize1.md)