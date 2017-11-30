---
title: "방법: 관찰자 구현"
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
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a964bd031f6f8a7fc029b2b209b9693b72e688af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-an-observer"></a>방법: 관찰자 구현
관찰자 디자인 패턴 나누기 알림을 등록 하는 관찰자 사이의 데이터를 모니터링 하 고 하나 이상의 관찰자에 게 알림을 전송 하 고 있는 공급자가 필요 합니다. 이 항목에서는 관찰자를 만드는 방법을 설명 합니다. 관련된 항목 [하는 방법: 공급자 구현](../../../docs/standard/events/how-to-implement-a-provider.md)는 공급자를 만드는 방법에 설명 합니다.  
  
### <a name="to-create-an-observer"></a>관찰자를 만들려면  
  
1.  관찰자를 구현 하는 유형 정의 <xref:System.IObserver%601?displayProperty=nameWithType> 인터페이스입니다. 다음 코드 이라는 형식을 정의 하는 예를 들어 `TemperatureReporter` 즉 생성 <xref:System.IObserver%601?displayProperty=nameWithType> 의 제네릭 형식 인수도 구현을 `Temperature`합니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  관찰자는 공급자 호출 하기 전에 알림 수신을 중지할 수 있는 경우 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현을 보유 하는 private 변수를 정의 <xref:System.IDisposable> 는 공급자에서 반환한 구현 <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> 메서드. 공급자를 호출 하는 구독 메서드를 정의 해야 <xref:System.IObservable%601.Subscribe%2A> 메서드 및 반환 된 저장소 <xref:System.IDisposable> 개체입니다. 다음 코드에서는 명명 된 전용 변수를 정의 하는 예를 들어 `unsubscriber` 정의 `Subscribe` 메서드는 공급자를 호출 하는 <xref:System.IObservable%601.Subscribe%2A> 메서드에 반환 된 개체를 할당 하 고는 `unsubscriber` 변수입니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  관찰자는 공급자 호출 하기 전에 알림 수신을 중지할 수 있는 메서드를 정의 합니다. 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현에서이 기능을 필요 합니다. 다음 예제에서는 정의 `Unsubscribe` 메서드.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  에 정의 된 세 가지 방법의 구현을 제공는 <xref:System.IObserver%601> 인터페이스: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, 및 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>합니다. 공급자 및 응용 프로그램의 요구에 따라는 <xref:System.IObserver%601.OnError%2A> 및 <xref:System.IObserver%601.OnCompleted%2A> 메서드 스텁 구현을 일 수 있습니다. <xref:System.IObserver%601.OnError%2A> 메서드가 전달 된 처리 해야 <xref:System.Exception> 예외로, 개체 및 <xref:System.IObserver%601.OnCompleted%2A> 메서드는 공급자의 어떤 이름이 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구현 합니다. 다음 예제와 <xref:System.IObserver%601> 구현의 `TemperatureReporter` 클래스입니다.  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a>예제  
 다음 예제에 대 한 전체 소스 코드에는 `TemperatureReporter` 클래스를 제공 하는 <xref:System.IObserver%601> 온도 모니터링 응용 프로그램에 대 한 구현 합니다.  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IObserver%601>  
 [관찰자 디자인 패턴](../../../docs/standard/events/observer-design-pattern.md)  
 [방법: 공급자 구현](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [관찰자 디자인 패턴 유용한 정보](../../../docs/standard/events/observer-design-pattern-best-practices.md)
