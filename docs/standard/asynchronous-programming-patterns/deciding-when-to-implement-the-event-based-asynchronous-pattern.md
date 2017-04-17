---
title: "Deciding When to Implement the Event-based Asynchronous Pattern | Microsoft Docs"
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
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "AsyncOperation class"
  - "AsyncCompletedEventArgs class"
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Deciding When to Implement the Event-based Asynchronous Pattern
이벤트 기반 비동기 패턴은 클래스의 비동기 동작을 노출하기 위한 패턴을 제공합니다.  이 패턴의 도입과 함께 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 비동기 동작을 노출하기 위한 두 가지 패턴인 <xref:System.IAsyncResult?displayProperty=fullName> 인터페이스 기반의 비동기 패턴과 이벤트 기반 패턴을 정의합니다.  이 항목에서는 이 두 패턴을 구현하는 적절한 시점에 대해 설명합니다.  
  
 <xref:System.IAsyncResult> 인터페이스를 사용한 비동기 프로그래밍에 대한 자세한 내용은 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)을 참조하십시오.  
  
## 일반 원칙  
 일반적으로 가능하면 이벤트 기반 비동기 패턴을 사용하여 비동기 기능을 노출해야 합니다.  그러나 이벤트 기반 패턴이 충족시킬 수 없는 몇 가지 요구 사항이 있습니다.  이러한 경우 이벤트 기반 패턴과 함께 <xref:System.IAsyncResult> 패턴을 구현해야 합니다.  
  
> [!NOTE]
>  이벤트 기반 패턴을 구현하지 않고 <xref:System.IAsyncResult> 패턴을 구현하는 경우는 거의 없습니다.  
  
## 지침  
 다음 목록에서는 이벤트 기반 비동기 패턴을 구현해야 하는 시점에 대한 지침을 설명합니다.  
  
-   클래스의 비동기 동작을 노출하려면 이벤트 기반 패턴을 기본 API로 사용합니다.  
  
-   Windows Forms과 같은 클라이언트 응용 프로그램에서 클래스가 주로 사용되는 경우 <xref:System.IAsyncResult> 패턴을 노출해서는 안 됩니다.  
  
-   요구 사항을 충족시키는 데 필요한 경우에만 <xref:System.IAsyncResult> 패턴을 노출합니다.  예를 들어, 기존 API와의 호환을 위해 <xref:System.IAsyncResult> 패턴을 노출해야 할 수 있습니다.  
  
-   이벤트 기반 패턴을 함께 노출하는 경우에만 <xref:System.IAsyncResult> 패턴을 노출합니다.  
  
-   <xref:System.IAsyncResult> 패턴을 노출해야 하는 경우 고급 옵션으로 노출합니다.  예를 들어, 프록시 개체를 생성하는 경우 <xref:System.IAsyncResult> 패턴을 생성하는 옵션을 사용하여 이벤트 기반 패턴을 기본적으로 생성합니다.  
  
-   <xref:System.IAsyncResult> 패턴 구현에서 이벤트 기반 패턴 구현을 빌드합니다.  
  
-   이벤트 기반 패턴과 <xref:System.IAsyncResult> 패턴을 동일한 클래스에 함께 노출하지 않습니다.  이벤트 기반 패턴을 "더 높은 수준" 클래스에 노출하고 <xref:System.IAsyncResult> 패턴을 “더 낮은 수준” 클래스에 노출합니다.  예를 들어, <xref:System.Net.WebClient> 구성 요소의 이벤트 기반 패턴과 <xref:System.Web.HttpRequest> 클래스의 <xref:System.IAsyncResult> 패턴을 비교합니다.  
  
    -   호환을 위해 필요한 경우 이벤트 기반 패턴과 <xref:System.IAsyncResult> 패턴을 동일한 클래스에 노출합니다.  예를 들어, <xref:System.IAsyncResult> 패턴을 사용하는 API를 이미 해제한 경우 이전 버전과의 호환성을 위해 <xref:System.IAsyncResult> 패턴을 유지해야 합니다.  
  
    -   구현을 구분하여 얻은 이점보다 결과로 만들어진 개체 모델의 복잡성으로 인한 부담이 큰 경우 이벤트 기반 패턴과 <xref:System.IAsyncResult> 패턴을 동일한 클래스에 노출합니다.  이벤트 기반 패턴을 노출하지 않는 것보다 단일 클래스에 두 패턴을 함께 노출하는 것이 더 좋습니다.  
  
    -   이벤트 기반 패턴과 <xref:System.IAsyncResult> 패턴을 단일 클래스에 함께 노출해야 하는 경우 <xref:System.ComponentModel.EditorBrowsableState>로 설정된 <xref:System.ComponentModel.EditorBrowsableAttribute>를 사용하여 <xref:System.IAsyncResult> 패턴 구현을 고급 기능으로 표시합니다.  이는 <xref:System.IAsyncResult> 속성과 메서드를 표시하는 것이 아니라 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] IntelliSense와 같은 환경을 설계하는 것을 의미합니다.  이러한 속성과 메서드는 아직도 충분히 사용할 수 있지만 IntelliSense에서 작업하는 개발자는 API를 보다 잘 볼 수 있습니다.  
  
## 이벤트 기반 패턴과 함께 IAsyncResult 패턴을 노출하기 위한 기준  
 이벤트 기반 비동기 패턴에는 앞서 언급한 시나리오에서 많은 장점이 있지만 성능이 가장 중요한 요구 사항인 경우 사용자가 알아야 하는 몇 가지 단점도 있습니다.  
  
 다음은 이벤트 기반 패턴이 <xref:System.IAsyncResult> 패턴과 마찬가지로 잘 처리할 수 없는 세 가지 시나리오입니다.  
  
-   하나의 <xref:System.IAsyncResult>에 대한 대기 차단  
  
-   여러 <xref:System.IAsyncResult> 개체에 대한 대기 차단  
  
-   <xref:System.IAsyncResult>의 완료에 대한 폴링  
  
 이벤트 기반 패턴을 사용하여 이러한 시나리오를 처리할 수는 있지만 이렇게 하는 것은 <xref:System.IAsyncResult> 패턴을 사용하는 것보다 어렵습니다.  
  
 개발자는 일반적으로 성능에 대한 요구 사항이 매우 높은 서비스에 <xref:System.IAsyncResult> 패턴을 사용합니다.  예를 들어, 완료에 대한 폴링 시나리오는 고성능 서버 기술입니다.  
  
 또한 이벤트 기반 패턴은 보다 많은 개체, 특히 보다 많은 <xref:System.EventArgs> 개체를 만들고 스레드를 동기화하므로 <xref:System.IAsyncResult> 패턴보다 효율성이 낮습니다.  
  
 다음 목록에서는 <xref:System.IAsyncResult> 패턴을 사용하려는 경우 준수해야 하는 몇 가지 권장 사항을 보여 줍니다.  
  
-   <xref:System.IAsyncResult> 패턴은 <xref:System.Threading.WaitHandle> 또는 <xref:System.IAsyncResult> 개체에 대한 지원이 특별히 필요한 경우에만 노출합니다.  
  
-   <xref:System.IAsyncResult> 패턴은 <xref:System.IAsyncResult> 패턴을 사용하는 기존 API가 있는 경우에만 노출합니다.  
  
-   <xref:System.IAsyncResult> 패턴을 기반으로 하는 기존 API가 있는 경우 다음 릴리스에 이벤트 기반 패턴을 노출하는 것도 고려합니다.  
  
-   <xref:System.IAsyncResult> 패턴은 높은 성능 요구 사항을 이벤트 기반 패턴으로는 충족시킬 수 없지만 <xref:System.IAsyncResult> 패턴으로는 충족시킬 수 있는 경우에만 노출합니다.  
  
## 참고 항목  
 [Walkthrough: Implementing a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)   
 [Multithreaded Programming with the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)   
 [Implementing the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)   
 [최선의 이벤트 기반 비동기 패턴 구현 방법](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)