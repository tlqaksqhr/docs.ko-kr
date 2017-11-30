---
title: "방법: 공급자 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observer design pattern [.NET Framework], implementing providers
- providers [.NET Framework], in observer design pattern
- observables [.NET Framework], in observer design pattern
ms.assetid: 790b5d8b-d546-40a6-beeb-151b574e5ee5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9d8f96de8cb3d13568e755f1d5e885e0474d891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-provider"></a>방법: 공급자 구현
관찰자 디자인 패턴에는 데이터를 모니터링 하 고 알림을 전송 하는 공급자 및 공급자에서 알림 (콜백)을 수신 하는 하나 이상의 관찰자 간의 구분이 필요 합니다. 이 항목에는 공급자를 만드는 방법을 설명 합니다. 관련된 항목 [하는 방법: 관찰자 구현](../../../docs/standard/events/how-to-implement-an-observer.md), 관찰자를 만드는 방법에 설명 합니다.  
  
### <a name="to-create-a-provider"></a>공급자를 만들려면  
  
1.  공급자는 관찰자에 게 전송 하는 데이터를 정의 합니다. 공급자와 관찰자에 게 전송 되는 데이터는 하나로 사용할 수 있지만 일반적으로 여러 형식으로 표시 됩니다. 예를 들어 온도 모니터링 응용 프로그램에에서는 `Temperature` 구조는 데이터를 정의 하는 공급자 (클래스로 표현 되는 `TemperatureMonitor` 다음 단계에 정의 된 클래스)를 모니터링 하 고 관찰자가 구독 합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  데이터 공급자를 구현 하는 형식을 정의 <xref:System.IObservable%601?displayProperty=nameWithType> 인터페이스입니다. 공급자의 제네릭 형식 인수는 형식 공급자는 관찰자에 게 전송입니다. 다음 예제에서는 정의 `TemperatureMonitor` 생성 된 클래스 <xref:System.IObservable%601?displayProperty=nameWithType> 의 제네릭 형식 인수도 구현을 `Temperature`합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  공급자는 저장 되는 방식과 관찰자에 대 한 참조 적절 한 경우에 각 관찰자를 알림을 받을 수 있도록 확인 합니다. 가장 일반적으로 같은 제네릭 컬렉션 개체 <xref:System.Collections.Generic.List%601> 개체는이 용도에 사용 됩니다. 다음 예제에서는 private <xref:System.Collections.Generic.List%601> 개체에서 인스턴스화되는 `TemperatureMonitor` 클래스 생성자입니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  정의 <xref:System.IDisposable> 공급자는 언제 든 지 알림 수신을 중지할 수 있도록 구독자에 게 반환할 수 있는 구현 합니다. 다음 예제에서는 중첩 된 정의 `Unsubscriber` 클래스를 인스턴스화할 때 구독자 컬렉션 하 고 구독자에 대 한 참조를 전달 되는 클래스입니다. 이 코드는 개체를 호출 하는 구독자를 통해 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구독자 컬렉션에서 제거할 자체 구현 합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> 메서드를 구현합니다. 메서드를 전달에 대 한 참조는 <xref:System.IObserver%601?displayProperty=nameWithType> 인터페이스 및 3 단계에서 해당 용도로 설계 된 개체에 저장 해야 합니다. 그런 다음 반환 해야는 <xref:System.IDisposable> 4 단계에서 개발 된 구현 합니다. 다음 예제에서는 구현의 <xref:System.IObservable%601.Subscribe%2A> 에서 메서드는 `TemperatureMonitor` 클래스입니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  호출 하 여 적절 하 게 관찰자가 알림 자신의 <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, 및 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현 합니다. 경우에 따라 공급자를 호출 하지 않을 수 있습니다는 <xref:System.IObserver%601.OnError%2A> 메서드 오류가 발생 합니다. 예를 들어, 다음 `GetTemperature` 메서드 5 초 마다 온도 데이터를 읽고 온도 이전 읽기 이후.1 각도 이상으로 변경 된 경우 관찰자에 게 알리는 하는 모니터를 시뮬레이션 합니다. 경우 (즉, 해당 값이 null 이면) 장치 온도 보고 하지 않습니다, 공급자 관찰자 전송이 완료 되었음을 알립니다. 이때 각 관찰자의 호출 하는 것 외에도 <xref:System.IObserver%601.OnCompleted%2A> 메서드를는 `GetTemperature` 메서드 지웁니다는 <xref:System.Collections.Generic.List%601> 컬렉션입니다. 공급자에 대 한 호출을 있게 하는 경우에 <xref:System.IObserver%601.OnError%2A> 해당 관찰자의 메서드.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 포함을 정의 하기 위한 전체 소스 코드는 <xref:System.IObservable%601> 온도 모니터링 응용 프로그램에 대 한 구현 합니다. 포함 된 `Temperature` 관찰자에 게 전송 되는 데이터 구조 및 `TemperatureMonitor` 클래스 즉는 <xref:System.IObservable%601> 구현 합니다.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IObservable%601>  
 [관찰자 디자인 패턴](../../../docs/standard/events/observer-design-pattern.md)  
 [방법: 관찰자 구현](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [관찰자 디자인 패턴 유용한 정보](../../../docs/standard/events/observer-design-pattern-best-practices.md)
