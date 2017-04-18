---
title: "Thread.Suspend, Garbage Collection, and Safe Points | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "suspending threads"
  - "safe points"
  - "threading [.NET Framework], suspending"
  - "threading [.NET Framework], garbage collection"
  - "garbage collection, threads"
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Thread.Suspend, Garbage Collection, and Safe Points
스레드에 대해 <xref:System.Threading.Thread.Suspend%2A?displayProperty=fullName>를 호출하면 시스템은 스레드 보류가 요청되었음을 감지하고 실제로 스레드를 일시 중단하기 전에 안전한 시점에 도달할 때까지 스레드가 실행될 수 있도록 합니다.  스레드의 안전한 시점은 실행 중에 가비지 수집을 수행할 수 있는 특정 시점입니다.  
  
 안전한 시점에 도달하면 런타임은 일시 중단된 스레드가 관리 코드에서 더 이상 진행되지 않도록 합니다.  관리 코드 외부에서 실행되는 스레드는 가비지 수집에 대해 항상 안전하며 관리 코드의 실행이 다시 시작될 때까지 계속 실행됩니다.  
  
> [!NOTE]
>  가비지 수집을 수행하려면 런타임은 수집을 수행 중인 스레드를 제외한 모든 스레드를 일시 중단해야 합니다.  스레드를 일시 중단하기 전에 각 스레드를 안전한 시점으로 가져와야 합니다.  
  
## 참고 항목  
 <xref:System.Threading.Thread>   
 <xref:System.GC>   
 [Threading](../../../docs/standard/threading/index.md)   
 [자동 메모리 관리](../../../docs/standard/automatic-memory-management.md)