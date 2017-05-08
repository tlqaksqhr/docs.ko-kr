---
title: "방법: 공급자 구현 | Microsoft Docs"
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
  - "관찰자 디자인 패턴[.NET Framework], 공급자 구현"
  - "공급자[.NET Framework], 관찰자 디자인 패턴"
  - "관찰 가능 개체[.NET Framework], 관찰자 디자인 패턴"
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 공급자 구현
관찰자 디자인 패턴을 사용하려면 데이터를 모니터링하고 알림을 전송하는 공급자와 공급자로부터 알림\(콜백\)을 수신하는 하나 이상의 관찰자 간의 구분이 필요합니다.  이 항목에서는 공급자를 만드는 방법을 설명합니다.  관련 항목, [방법: 관찰자 구현](../../../docs/standard/events/how-to-implement-an-observer.md)에서는 관찰자를 만드는 방법에 대해 설명합니다.  
  
### 공급자를 만들려면  
  
1.  공급자가 관찰자에게 전송해야 하는 데이터를 정의합니다.  공급자 및 공급자가 관찰자에게 전송하는 데이터는 단일 형식일 수 있지만 일반적으로 여러 형식으로 표시됩니다.  예를 들어 온도 모니터링 응용 프로그램에서 `Temperature` 구조체는 공급자\(다음 단계에서 정의된 `TemperatureMonitor` 클래스로 표시됨\)가 모니터링하고 관찰자가 구독하는 데이터를 정의합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  <xref:System.IObservable%601?displayProperty=fullName> 인터페이스를 구현하는 형식인 데이터 공급자를 정의합니다.  공급자의 제네릭 형식 인수는 공급자가 관찰자에게 전송하는 형식입니다.  다음 예제에서는 `Temperature`의 제네릭 형식 인수를 사용하여 생성된 <xref:System.IObservable%601?displayProperty=fullName> 구현인 `TemperatureMonitor` 클래스를 정의합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  적합한 시기에 각 관찰자에게 알림을 제공할 수 있도록 공급자가 관찰자에 대한 참조를 저장하는 방법을 결정합니다.  가장 일반적으로 제네릭 <xref:System.Collections.Generic.List%601> 개체와 같은 컬렉션 개체가 이 용도로 사용됩니다.  다음 예제에서는 `TemperatureMonitor` 클래스 생성자에 인스턴스화된 전용 <xref:System.Collections.Generic.List%601> 개체를 정의합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  구독자가 언제라도 알림 수신을 중지할 수 있도록 공급자가 구독자에게 반환할 수 있는 <xref:System.IDisposable> 구현을 정의합니다.  다음 예제에서는 클래스가 인스턴스화될 때 구독자 컬렉션 및 구독자에 대한 참조가 전달되는 중첩된 `Unsubscriber` 클래스를 정의합니다.  이 코드는 구독자가 개체의 <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> 구현을 호출하여 구독자 컬렉션에서 자신을 제거할 수 있게 해줍니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  <xref:System.IObservable%601.Subscribe%2A?displayProperty=fullName> 메서드를 구현합니다.  이 메서드에는 <xref:System.IObserver%601?displayProperty=fullName> 인터페이스에 대한 참조가 전달되며, 3단계에서 해당 목적으로 디자인된 개체에 메서드가 저장되어야 합니다.  그런 다음 메서드는 4단계에서 개발된 <xref:System.IDisposable> 구현을 반환합니다.  다음 예제에서는 `TemperatureMonitor` 클래스에서 <xref:System.IObservable%601.Subscribe%2A> 메서드의 구현을 보여 줍니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  필요에 따라 <xref:System.IObserver%601.OnNext%2A?displayProperty=fullName>, <xref:System.IObserver%601.OnError%2A?displayProperty=fullName> 및 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=fullName> 구현을 호출하여 관찰자에게 알림을 제공합니다.  일부 경우에는 오류가 발생할 때 공급자가 <xref:System.IObserver%601.OnError%2A> 메서드를 호출하지 않을 수 있습니다.  예를 들어 다음 `GetTemperature` 메서드는 5초 간격으로 온도 데이터를 읽는 모니터를 시뮬레이션하고 이전 수치에서 최소한 1도 이상 온도가 변경된 경우 관찰자에게 이를 알립니다.  장치가 온도를 보고하지 않을 경우\(즉, 값이 null인 경우\) 공급자가 관찰자에게 전송이 완료되었음을 알립니다.  각 관찰자의 <xref:System.IObserver%601.OnCompleted%2A> 메서드를 호출하는 것 외에도 `GetTemperature` 메서드는 <xref:System.Collections.Generic.List%601> 컬렉션을 지웁니다.  이 경우 공급자는 해당 관찰자의 <xref:System.IObserver%601.OnError%2A> 메서드를 호출하지 않습니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## 예제  
 다음 예제에는 온도 모니터링 응용 프로그램을 위해 <xref:System.IObservable%601> 구현을 정의하기 위한 전체 소스 코드가 포함되어 있습니다.  여기에는 관찰자에게 전송되는 데이터인 `Temperature` 구조체와 <xref:System.IObservable%601> 구현인 `TemperatureMonitor` 클래스가 포함됩니다.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## 참고 항목  
 <xref:System.IObservable%601>   
 [관찰자 디자인 패턴](../../../docs/standard/events/observer-design-pattern.md)   
 [방법: 관찰자 구현](../../../docs/standard/events/how-to-implement-an-observer.md)   
 [관찰자 디자인 패턴 유용한 정보](../../../docs/standard/events/observer-design-pattern-best-practices.md)