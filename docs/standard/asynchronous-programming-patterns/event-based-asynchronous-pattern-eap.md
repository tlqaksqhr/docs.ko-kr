---
title: 이벤트 기반 비동기 패턴(EAP)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
caps.latest.revision: 20
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fecd71355d53f1e3937d3724569b10fa0c8e50da
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="event-based-asynchronous-pattern-eap"></a>이벤트 기반 비동기 패턴(EAP)
비동기 기능을 클라이언트 코드에 노출하는 방법은 여러 가지가 있습니다. 이벤트 기반 비동기 패턴은 클래스에 비동기 동작을 표시하는 한 가지 방법을 규정합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 작업 병렬 라이브러리에서 비동기 및 병렬 프로그래밍을 위한 새로운 모델을 제공합니다. 자세한 내용은 [병렬 프로그래밍](../../../docs/standard/parallel-programming/index.md)을 참조하세요.  
  
## <a name="in-this-section"></a>섹션 내용  
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
  
## <a name="related-sections"></a>관련 단원  
 [TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 비동기 및 병렬 작업용 프로그래밍 모델에 대해 설명합니다.  
  
 [스레딩](../../../docs/standard/threading/index.md)  
 .NET Framework 다중 스레딩 기능에 대해 설명합니다.  
  
 [스레딩](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 C# 및 Visual Basic 언어의 다중 스레딩 기능에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [관리되는 스레딩을 구현하는 최선의 방법](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [이벤트](../../../docs/standard/events/index.md)  
 [구성 요소에서 다중 스레딩](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [비동기 프로그래밍 패턴](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
