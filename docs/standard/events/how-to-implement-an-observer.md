---
title: "방법: 관찰자 구현 | Microsoft Docs"
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
  - "관찰자[.NET Framework], 관찰자 디자인 패턴"
  - "관찰자 디자인 패턴[.NET Framework], 관찰자 구현"
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 관찰자 구현
관찰자 디자인 패턴을 사용하려면 알림을 등록하는 관찰자와 데이터를 모니터링하고 하나 이상의 관찰자에게 알림을 전송하는 공급자 간의 구분이 필요합니다.  이 항목에서는 관찰자를 만드는 방법에 대해 설명합니다.  관련 항목, [방법: 공급자 구현](../../../docs/standard/events/how-to-implement-a-provider.md)에서는 공급자를 만드는 방법에 대해 설명합니다.  
  
### 관찰자를 만들려면  
  
1.  <xref:System.IObserver%601?displayProperty=fullName> 인터페이스를 구현하는 형식의 관찰자를 정의합니다.  예를 들어 다음 코드에서는 `Temperature`의 제네릭 형식 인수를 사용하여 생성된 <xref:System.IObserver%601?displayProperty=fullName> 구현인 `TemperatureReporter`라는 이름의 형식을 정의합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  공급자가 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName> 구현을 호출하기 전에 관찰자가 알림 수신을 중지할 수 있는 경우, 공급자의 <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName> 메서드로 반환된 <xref:System.IDisposable> 구현을 저장하는 전용 변수를 정의합니다.  또한 공급자의 <xref:System.IObservable%601.Subscribe%2A> 메서드를 호출하고 반환된 <xref:System.IDisposable> 개체를 저장하는 구독 메서드를 정의해야 합니다.  예를 들어 다음 코드에서는 `unsubscriber`라는 전용 변수를 정의하고, 공급자의 <xref:System.IObservable%601.Subscribe%2A> 메서드를 호출하고 반환된 개체를 `unsubscriber` 변수에 할당하는 `Subscribe` 메서드를 정의합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  이 기능이 필요한 경우 공급자가 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName> 구현을 호출하기 전 관찰자가 알림 수신을 중지할 수 있게 해주는 메서드를 정의합니다.  다음 예제에서는 `Unsubscribe` 메서드를 정의합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <xref:System.IObserver%601> 인터페이스로 정의된 세 가지 메서드 <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> 및 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName>에 대한 구현을 제공합니다.  공급자 및 응용 프로그램의 요구 사항에 따라 <xref:System.IObserver%601.OnError%2A> 및 <xref:System.IObserver%601.OnCompleted%2A> 메서드는 스텁 구현일 수 있습니다.  <xref:System.IObserver%601.OnError%2A> 메서드는 전달된 <xref:System.Exception> 개체를 예외로 처리하지 않아야 하며, <xref:System.IObserver%601.OnCompleted%2A> 메서드가 공급자의 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 구현을 자유롭게 호출할 수 있어야 합니다.  다음 예에서는 `TemperatureReporter` 클래스의 <xref:System.IObserver%601> 구현을 보여 줍니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## 예제  
 다음 예에는 온도 모니터링 응용 프로그램을 위해 <xref:System.IObserver%601> 구현을 제공하는 `TemperatureReporter` 클래스에 대한 전체 소스 코드가 포함되어 있습니다.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## 참고 항목  
 <xref:System.IObserver%601>   
 [관찰자 디자인 패턴](../../../docs/standard/events/observer-design-pattern.md)   
 [방법: 공급자 구현](../../../docs/standard/events/how-to-implement-a-provider.md)   
 [관찰자 디자인 패턴 유용한 정보](../../../docs/standard/events/observer-design-pattern-best-practices.md)