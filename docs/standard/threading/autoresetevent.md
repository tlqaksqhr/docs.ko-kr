---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a>AutoResetEvent
<xref:System.Threading.AutoResetEvent> 대기 스레드 하나를 해제 한 후 신호를 받을 때 자동으로 다시 설정 하는 로컬 대기 핸들 이벤트 클래스를 나타냅니다. 이 클래스는 기본 클래스의 특수 한 경우를 나타냅니다. <xref:System.Threading.EventWaitHandle>합니다. 자동 재설정 이벤트의 사용 및 기능은 [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) 개념 설명서를 참조하세요.  
  
 <xref:System.Threading.AutoResetEvent> 개체는 자동으로 다시 설정에 신호 시스템에서 대기 중인 단일 스레드가 해제 된 후입니다. 대기 스레드가 없으면 이벤트 개체의 상태는 신호를 받은 것으로 유지됩니다. <xref:System.Threading.AutoResetEvent>해당 하는 Win32 `CreateEvent` 지정 함으로써 호출 `false` 에 대 한는 `bManualReset` 인수입니다.  
  
 사용 하는 예제에 대 한 <xref:System.Threading.AutoResetEvent>, 참조 [모니터](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [스레딩](../../../docs/standard/threading/index.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)  
 [대기 핸들](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
