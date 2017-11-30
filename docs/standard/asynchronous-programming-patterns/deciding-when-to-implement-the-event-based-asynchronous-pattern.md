---
title: "이벤트 기반 비동기 패턴 구현 시기 결정"
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
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>이벤트 기반 비동기 패턴 구현 시기 결정
이벤트 기반 비동기 패턴 클래스의 비동기 동작을 노출 하기 위한 패턴을 제공 합니다. 이 패턴의 도입으로는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 비동기 동작을 노출 하기 위한 두 개의 패턴 정의: 비동기 패턴에 따라는 <xref:System.IAsyncResult?displayProperty=nameWithType> 인터페이스 및 이벤트 기반 패턴입니다. 이 항목에서는 두 패턴을 구현 하기 위한 적절 한 경우를 설명 합니다.  
  
 비동기 프로그래밍에 대 한 자세한 내용은 <xref:System.IAsyncResult> 인터페이스를 참조 [이벤트 기반 비동기 패턴 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)합니다.  
  
## <a name="general-principles"></a>일반 원칙  
 일반적으로 가능 하면 이벤트 기반 비동기 패턴을 사용 하 여 비동기 기능을 노출 해야 합니다. 그러나 이벤트 기반 패턴 충족할 수 없는 몇 가지 요구 사항이 있습니다. 구현 해야 이러한 경우에는 <xref:System.IAsyncResult> 이벤트 기반 패턴 외에도 패턴입니다.  
  
> [!NOTE]
>  경우는 거의 <xref:System.IAsyncResult> 패턴 구현 되 고 이벤트 기반 패턴 없이 구현 합니다.  
  
## <a name="guidelines"></a>지침  
 다음 목록에서는 이벤트 기반 비동기 패턴을 구현 해야 하는 경우에 대 한 지침을 설명 합니다.  
  
-   기본 API로 이벤트 기반 패턴을 사용 하 여 클래스에 대 한 비동기 동작을 노출 합니다.  
  
-   노출 하지 마십시오.는 <xref:System.IAsyncResult> 클래스는 주로 Windows Forms 클라이언트 응용 프로그램에서 사용 하는 경우 패턴을 사용 합니다.  
  
-   노출 된 <xref:System.IAsyncResult> 요구 사항을 충족 해야 하는 경우 패턴을 사용 합니다. 예를 들어 기존 API와의 호환성을 노출 해야 할 수도 있습니다는 <xref:System.IAsyncResult> 패턴입니다.  
  
-   노출 하지 마십시오.는 <xref:System.IAsyncResult> 도 이벤트 기반 패턴을 노출 하지 않고 패턴입니다.  
  
-   노출 해야 하는 경우는 <xref:System.IAsyncResult> 고급 옵션으로, 패턴을 사용 합니다. 예를 들어 프록시 개체를 생성 하는 경우 생성 이벤트 기반 패턴 기본적으로 생성 하는 옵션으로는 <xref:System.IAsyncResult> 패턴입니다.  
  
-   이벤트 기반 패턴 구현을 토대로 사용자 <xref:System.IAsyncResult> 패턴 구현 합니다.  
  
-   두 이벤트 기반 패턴을 노출 하지 마십시오. 및 <xref:System.IAsyncResult> 동일한 클래스에는 패턴입니다. "상위" 클래스에 따라 이벤트 패턴을 노출 및 <xref:System.IAsyncResult> 패턴을 "더 낮은 수준" 클래스입니다. 예를 들어, 이벤트 기반 패턴의 비교는 <xref:System.Net.WebClient> 구성 요소는 <xref:System.IAsyncResult> 패턴에 <xref:System.Web.HttpRequest> 클래스.  
  
    -   이벤트 기반 패턴을 노출 및 <xref:System.IAsyncResult> 패턴 호환성 필요로 하는 경우 동일한 클래스에 있습니다. 예를 들어, 이미 사용 하는 API를 해제 하는 경우는 <xref:System.IAsyncResult> 패턴을 유지 해야 할 것은 <xref:System.IAsyncResult> 이전 버전과 호환성에 대 한 패턴입니다.  
  
    -   이벤트 기반 패턴을 노출 및 <xref:System.IAsyncResult> 결과 개체 모델의 복잡성 구현을 구분 하 여 얻은 이점 보다 하는 경우 동일한 클래스에 패턴입니다. 이벤트 기반 패턴을 노출 하지 않는 것 보다는 단일 클래스에 두 패턴을 노출 하는 것이 좋습니다.  
  
    -   두 이벤트 기반 패턴을 노출 해야 하는 경우 및 <xref:System.IAsyncResult> 패턴에서 단일 클래스를 사용 하 여 <xref:System.ComponentModel.EditorBrowsableAttribute> 로 설정 <xref:System.ComponentModel.EditorBrowsableState.Advanced> 표시 하는 <xref:System.IAsyncResult> 는 고급 기능으로 패턴 구현 합니다. 디자인 환경에 같은 나타냅니다 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 를 나타내지 IntelliSense는 <xref:System.IAsyncResult> 속성 및 메서드. 이러한 속성 및 메서드는 계속 완벽 하 게 사용할 수 있지만 IntelliSense를 통해 작업 하는 개발자가 API 확인 합니다.  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>이벤트 기반 패턴 외에도 IAsyncResult 패턴을 노출 하는 것에 대 한 기준  
 이벤트 기반 비동기 패턴에는 앞에서 언급 한 시나리오에서 많은 장점이, 성능이 가장 중요 한 요구 사항 경우 알고 있어야 하는 몇 가지 장애가 들어지 않습니다.  
  
 이벤트 기반 패턴 해결 되지 않는 세 가지 시나리오가 있습니다으로 <xref:System.IAsyncResult> 패턴:  
  
-   대기 하나에 차단<xref:System.IAsyncResult>  
  
-   많은 대기 차단 <xref:System.IAsyncResult> 개체  
  
-   완료에 대 한 폴링는<xref:System.IAsyncResult>  
  
 이벤트 기반 패턴을 사용 하 여 이러한 시나리오를 처리할 수 있지만 방법은 사용 하 여 보다 성가 십니다는 <xref:System.IAsyncResult> 패턴입니다.  
  
 개발자는 종종 사용 된 <xref:System.IAsyncResult> 일반적으로 매우 높은 성능 요구 사항이 서비스에 대 한 패턴입니다. 예를 들어 완료 시나리오에 대 한 폴링은 고성능 서버 기술 합니다.  
  
 또한, 이벤트 기반 패턴은 것 보다는 <xref:System.IAsyncResult> 특히 더 많은 개체를 만들기 때문에 패턴 <xref:System.EventArgs>, 때문이 스레드를 동기화 합니다.  
  
 다음 목록은 몇 가지 권장 사항 사용 하려는 경우 수행 하는 <xref:System.IAsyncResult> 패턴:  
  
-   표시는 <xref:System.IAsyncResult> 패턴에 대 한 지원 특별히 필요한 경우 <xref:System.Threading.WaitHandle> 또는 <xref:System.IAsyncResult> 개체입니다.  
  
-   노출 된 <xref:System.IAsyncResult> 사용 하는 기존 API가 있는 경우는 <xref:System.IAsyncResult> 패턴입니다.  
  
-   기반으로 하는 기존 API가 있는 경우는 <xref:System.IAsyncResult> 도 다음 릴리스에 따라 이벤트 패턴을 노출 하는 것이 좋습니다., 패턴을 사용 합니다.  
  
-   주요 <xref:System.IAsyncResult> 패턴 있는 고성능 요구 사항이 있는 경우 이벤트 기반 패턴에 맞지 않습니다 하지만 하 여 충족할 수는 <xref:System.IAsyncResult> 패턴입니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 이벤트 기반 비동기 패턴을 지원하는 구성 요소 구현](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [이벤트 기반 비동기 패턴을 사용한 다중 스레드 프로그래밍](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [이벤트 기반 비동기 패턴 구현](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [최선의 이벤트 기반 비동기 패턴 구현 방법](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
