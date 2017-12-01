---
title: "Thread.Suspend, 가비지 컬렉션, 안전한 시점"
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
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Thread.Suspend, 가비지 컬렉션, 안전한 시점
호출 하는 경우 <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> 스레드에서 시스템 정보 스레드 일시 중단 요청 되었습니다. 및 스레드 실제로 스레드가 일시 중단 하기 전에 안전한 시점에도 달했기 해질 때까지 실행할 수 있습니다. 스레드에 대 한 안전한 시점에는 가비지 수집을 수행할 수 실행 중에 요소를입니다.  
  
 안전한 시점에 도달 하면 런타임에서 일시 중지 된 스레드는 관리 코드에서 더 이상 진행을 있게 되지 보장 합니다. 관리 되는 코드 외부에서 실행 스레드는 항상 가비지 수집에 대 한 안전 하 게 보호 및 관리 코드의 실행을 다시 시작 될 때까지 계속 실행 됩니다.  
  
> [!NOTE]
>  가비지 수집을 수행 하려면 런타임에 수집을 수행 중인 스레드를 제외한 모든 스레드를 일시 중지 해야 합니다. 각 스레드를 일시 중단할 수 전에 안전한 시점으로 가져와야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [스레딩](../../../docs/standard/threading/index.md)  
 [자동 메모리 관리](../../../docs/standard/automatic-memory-management.md)
