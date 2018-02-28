---
title: "Thread.Suspend, 가비지 수집, 안전한 시점"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fdd56763712dee9c6fa1f292eb3bbb2f0ccbf505
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, 가비지 수집, 안전한 시점
스레드에서 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>를 호출하면 시스템에서 스레드 일시 중단이 요청되었음을 인식하고 스레드를 실제로 일시 중단하기 전에 안전 지점에 도달할 때까지 스레드가 실행되도록 합니다. 스레드의 안전 지점은 가비지 수집을 수행할 수 있는 실행 지점입니다.  
  
 안전 지점에 도달하면 런타임에서 일시 중단된 스레드가 관리 코드에서 더 이상 진행되지 않도록 보장합니다. 관리 코드 외부에서 실행하는 스레드는 가비지 수집에 대해 항상 안전하며 관리 코드의 실행을 다시 시작하려고 할 때까지 실행이 계속됩니다.  
  
> [!NOTE]
>  가비지 수집을 수행하기 위해 런타임은 수집을 수행하는 스레드를 제외한 모든 스레드를 일시 중단해야 합니다. 일시 중단하기 전에 각 스레드를 안전 지점으로 가져와야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [스레딩](../../../docs/standard/threading/index.md)  
 [자동 메모리 관리](../../../docs/standard/automatic-memory-management.md)
