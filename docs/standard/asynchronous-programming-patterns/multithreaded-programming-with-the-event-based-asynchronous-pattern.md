---
title: "이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: 958d6617-5e70-4b36-b5db-63c16dc35e43
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7a26f6750f68609b40e6917fc5b257e43d95c3c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="multithreaded-programming-with-the-event-based-asynchronous-pattern"></a>이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍
비동기 기능을 클라이언트 코드에 노출하는 방법은 여러 가지가 있습니다. 이벤트 기반 비동기 패턴은 클래스에 비동기 동작을 표시하는 권장 방법을 규정합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 이벤트 기반 비동기 패턴이 다중 스레드 디자인에 본질적으로 존재하는 복잡한 여러 가지 문제를 숨기면서 다중 스레드 응용 프로그램의 장점을 이용할 수 있게 해주는 방법을 설명합니다.  
  
 [이벤트 기반 비동기 패턴 구현](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 비동기 기능을 포함하는 클래스를 패키징하는 표준화된 방법을 설명합니다.  
  
 [최선의 이벤트 기반 비동기 패턴 구현 방법](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 이벤트 기반 비동기 패턴에 따라 비동기 기능을 노출하기 위한 요구 사항을 설명합니다.  
  
 [이벤트 기반 비동기 패턴 구현 시기 결정](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 <xref:System.IAsyncResult> 패턴 대신 이벤트 기반 비동기 패턴을 구현하도록 선택해야 하는 경우를 확인하는 방법을 설명합니다.  
  
 [연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 이벤트 기반 비동기 패턴을 구현하는 구성 요소를 만드는 방법을 보여 줍니다. 구성 요소가 모든 응용 프로그램 모델에서 올바르게 작동하도록 하는 <xref:System.ComponentModel?displayProperty=nameWithType> 네임스페이스의 도우미 클래스를 사용하는 것이 좋습니다.  
  
 [방법: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 사용](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 이벤트 기반 비동기 패턴을 지원하는 구성 요소를 사용하는 방법을 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ComponentModel.AsyncOperation>  
 <xref:System.ComponentModel.AsyncOperation> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 <xref:System.ComponentModel.AsyncOperationManager> 클래스를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 설명하고 모든 해당 멤버의 링크를 포함합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 스레딩을 구현하는 최선의 방법](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [이벤트](../../../docs/standard/events/index.md)  
 [구성 요소에서 다중 스레딩](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
