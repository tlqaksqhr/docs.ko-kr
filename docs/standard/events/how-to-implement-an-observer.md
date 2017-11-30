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
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="9ee98-102">방법: 관찰자 구현</span><span class="sxs-lookup"><span data-stu-id="9ee98-102">How to: Implement an Observer</span></span>
<span data-ttu-id="9ee98-103">관찰자 디자인 패턴 나누기 알림을 등록 하는 관찰자 사이의 데이터를 모니터링 하 고 하나 이상의 관찰자에 게 알림을 전송 하 고 있는 공급자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="9ee98-104">이 항목에서는 관찰자를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="9ee98-105">관련된 항목 [하는 방법: 공급자 구현](../../../docs/standard/events/how-to-implement-a-provider.md)는 공급자를 만드는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-105">A related topic, [How to: Implement a Provider](../../../docs/standard/events/how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="9ee98-106">관찰자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="9ee98-106">To create an observer</span></span>  
  
1.  <span data-ttu-id="9ee98-107">관찰자를 구현 하는 유형 정의 <xref:System.IObserver%601?displayProperty=nameWithType> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="9ee98-108">다음 코드 이라는 형식을 정의 하는 예를 들어 `TemperatureReporter` 즉 생성 <xref:System.IObserver%601?displayProperty=nameWithType> 의 제네릭 형식 인수도 구현을 `Temperature`합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  <span data-ttu-id="9ee98-109">관찰자는 공급자 호출 하기 전에 알림 수신을 중지할 수 있는 경우 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현을 보유 하는 private 변수를 정의 <xref:System.IDisposable> 는 공급자에서 반환한 구현 <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9ee98-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="9ee98-110">공급자를 호출 하는 구독 메서드를 정의 해야 <xref:System.IObservable%601.Subscribe%2A> 메서드 및 반환 된 저장소 <xref:System.IDisposable> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="9ee98-111">다음 코드에서는 명명 된 전용 변수를 정의 하는 예를 들어 `unsubscriber` 정의 `Subscribe` 메서드는 공급자를 호출 하는 <xref:System.IObservable%601.Subscribe%2A> 메서드에 반환 된 개체를 할당 하 고는 `unsubscriber` 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  <span data-ttu-id="9ee98-112">관찰자는 공급자 호출 하기 전에 알림 수신을 중지할 수 있는 메서드를 정의 합니다. 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현에서이 기능을 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="9ee98-113">다음 예제에서는 정의 `Unsubscribe` 메서드.</span><span class="sxs-lookup"><span data-stu-id="9ee98-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <span data-ttu-id="9ee98-114">에 정의 된 세 가지 방법의 구현을 제공는 <xref:System.IObserver%601> 인터페이스: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, 및 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9ee98-115">공급자 및 응용 프로그램의 요구에 따라는 <xref:System.IObserver%601.OnError%2A> 및 <xref:System.IObserver%601.OnCompleted%2A> 메서드 스텁 구현을 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="9ee98-116"><xref:System.IObserver%601.OnError%2A> 메서드가 전달 된 처리 해야 <xref:System.Exception> 예외로, 개체 및 <xref:System.IObserver%601.OnCompleted%2A> 메서드는 공급자의 어떤 이름이 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="9ee98-117">다음 예제와 <xref:System.IObserver%601> 구현의 `TemperatureReporter` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="9ee98-118">예제</span><span class="sxs-lookup"><span data-stu-id="9ee98-118">Example</span></span>  
 <span data-ttu-id="9ee98-119">다음 예제에 대 한 전체 소스 코드에는 `TemperatureReporter` 클래스를 제공 하는 <xref:System.IObserver%601> 온도 모니터링 응용 프로그램에 대 한 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ee98-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="9ee98-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ee98-120">See Also</span></span>  
 <xref:System.IObserver%601>  
 [<span data-ttu-id="9ee98-121">관찰자 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="9ee98-121">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="9ee98-122">방법: 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="9ee98-122">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [<span data-ttu-id="9ee98-123">관찰자 디자인 패턴 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="9ee98-123">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
