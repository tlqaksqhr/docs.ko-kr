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
# <a name="how-to-implement-a-provider"></a><span data-ttu-id="74056-102">방법: 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="74056-102">How to: Implement a Provider</span></span>
<span data-ttu-id="74056-103">관찰자 디자인 패턴에는 데이터를 모니터링 하 고 알림을 전송 하는 공급자 및 공급자에서 알림 (콜백)을 수신 하는 하나 이상의 관찰자 간의 구분이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-103">The observer design pattern requires a division between a provider, which monitors data and sends notifications, and one or more observers, which receive notifications (callbacks) from the provider.</span></span> <span data-ttu-id="74056-104">이 항목에는 공급자를 만드는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-104">This topic discusses how to create a provider.</span></span> <span data-ttu-id="74056-105">관련된 항목 [하는 방법: 관찰자 구현](../../../docs/standard/events/how-to-implement-an-observer.md), 관찰자를 만드는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-105">A related topic, [How to: Implement an Observer](../../../docs/standard/events/how-to-implement-an-observer.md), discusses how to create an observer.</span></span>  
  
### <a name="to-create-a-provider"></a><span data-ttu-id="74056-106">공급자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="74056-106">To create a provider</span></span>  
  
1.  <span data-ttu-id="74056-107">공급자는 관찰자에 게 전송 하는 데이터를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-107">Define the data that the provider is responsible for sending to observers.</span></span> <span data-ttu-id="74056-108">공급자와 관찰자에 게 전송 되는 데이터는 하나로 사용할 수 있지만 일반적으로 여러 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74056-108">Although the provider and the data that it sends to observers can be a single type, they are generally represented by different types.</span></span> <span data-ttu-id="74056-109">예를 들어 온도 모니터링 응용 프로그램에에서는 `Temperature` 구조는 데이터를 정의 하는 공급자 (클래스로 표현 되는 `TemperatureMonitor` 다음 단계에 정의 된 클래스)를 모니터링 하 고 관찰자가 구독 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-109">For example, in a temperature monitoring application, the `Temperature` structure defines the data that the provider (which is represented by the `TemperatureMonitor` class defined in the next step) monitors and to which observers subscribe.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/data.cs#1)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/data.vb#1)]  
  
2.  <span data-ttu-id="74056-110">데이터 공급자를 구현 하는 형식을 정의 <xref:System.IObservable%601?displayProperty=nameWithType> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="74056-110">Define the data provider, which is a type that implements the <xref:System.IObservable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="74056-111">공급자의 제네릭 형식 인수는 형식 공급자는 관찰자에 게 전송입니다.</span><span class="sxs-lookup"><span data-stu-id="74056-111">The provider's generic type argument is the type that the provider sends to observers.</span></span> <span data-ttu-id="74056-112">다음 예제에서는 정의 `TemperatureMonitor` 생성 된 클래스 <xref:System.IObservable%601?displayProperty=nameWithType> 의 제네릭 형식 인수도 구현을 `Temperature`합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-112">The following example defines a `TemperatureMonitor` class, which is a constructed <xref:System.IObservable%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#2)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#2)]  
  
3.  <span data-ttu-id="74056-113">공급자는 저장 되는 방식과 관찰자에 대 한 참조 적절 한 경우에 각 관찰자를 알림을 받을 수 있도록 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-113">Determine how the provider will store references to observers so that each observer can be notified when appropriate.</span></span> <span data-ttu-id="74056-114">가장 일반적으로 같은 제네릭 컬렉션 개체 <xref:System.Collections.Generic.List%601> 개체는이 용도에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74056-114">Most commonly, a collection object such as a generic <xref:System.Collections.Generic.List%601> object is used for this purpose.</span></span> <span data-ttu-id="74056-115">다음 예제에서는 private <xref:System.Collections.Generic.List%601> 개체에서 인스턴스화되는 `TemperatureMonitor` 클래스 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="74056-115">The following example defines a private <xref:System.Collections.Generic.List%601> object that is instantiated in the `TemperatureMonitor` class constructor.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#3)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#3)]  
  
4.  <span data-ttu-id="74056-116">정의 <xref:System.IDisposable> 공급자는 언제 든 지 알림 수신을 중지할 수 있도록 구독자에 게 반환할 수 있는 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-116">Define an <xref:System.IDisposable> implementation that the provider can return to subscribers so that they can stop receiving notifications at any time.</span></span> <span data-ttu-id="74056-117">다음 예제에서는 중첩 된 정의 `Unsubscriber` 클래스를 인스턴스화할 때 구독자 컬렉션 하 고 구독자에 대 한 참조를 전달 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="74056-117">The following example defines a nested `Unsubscriber` class that is passed a reference to the subscribers collection and to the subscriber when the class is instantiated.</span></span> <span data-ttu-id="74056-118">이 코드는 개체를 호출 하는 구독자를 통해 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구독자 컬렉션에서 제거할 자체 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-118">This code enables the subscriber to call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation to remove itself from the subscribers collection.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#4)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#4)]  
  
5.  <span data-ttu-id="74056-119"><xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-119">Implement the <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="74056-120">메서드를 전달에 대 한 참조는 <xref:System.IObserver%601?displayProperty=nameWithType> 인터페이스 및 3 단계에서 해당 용도로 설계 된 개체에 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-120">The method is passed a reference to the <xref:System.IObserver%601?displayProperty=nameWithType> interface and should be stored in the object designed for that purpose in step 3.</span></span> <span data-ttu-id="74056-121">그런 다음 반환 해야는 <xref:System.IDisposable> 4 단계에서 개발 된 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-121">The method should then return the <xref:System.IDisposable> implementation developed in step 4.</span></span> <span data-ttu-id="74056-122">다음 예제에서는 구현의 <xref:System.IObservable%601.Subscribe%2A> 에서 메서드는 `TemperatureMonitor` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="74056-122">The following example shows the implementation of the <xref:System.IObservable%601.Subscribe%2A> method in the `TemperatureMonitor` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#5)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#5)]  
  
6.  <span data-ttu-id="74056-123">호출 하 여 적절 하 게 관찰자가 알림 자신의 <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, 및 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-123">Notify observers as appropriate by calling their <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementations.</span></span> <span data-ttu-id="74056-124">경우에 따라 공급자를 호출 하지 않을 수 있습니다는 <xref:System.IObserver%601.OnError%2A> 메서드 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-124">In some cases, a provider may not call the <xref:System.IObserver%601.OnError%2A> method when an error occurs.</span></span> <span data-ttu-id="74056-125">예를 들어, 다음 `GetTemperature` 메서드 5 초 마다 온도 데이터를 읽고 온도 이전 읽기 이후.1 각도 이상으로 변경 된 경우 관찰자에 게 알리는 하는 모니터를 시뮬레이션 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-125">For example, the following `GetTemperature` method simulates a monitor that reads temperature data every five seconds and notifies observers if the temperature has changed by at least .1 degree since the previous reading.</span></span> <span data-ttu-id="74056-126">경우 (즉, 해당 값이 null 이면) 장치 온도 보고 하지 않습니다, 공급자 관찰자 전송이 완료 되었음을 알립니다.</span><span class="sxs-lookup"><span data-stu-id="74056-126">If the device does not report a temperature (that is, if its value is null), the provider notifies observers that the transmission is complete.</span></span> <span data-ttu-id="74056-127">이때 각 관찰자의 호출 하는 것 외에도 <xref:System.IObserver%601.OnCompleted%2A> 메서드를는 `GetTemperature` 메서드 지웁니다는 <xref:System.Collections.Generic.List%601> 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="74056-127">Note that, in addition to calling each observer's <xref:System.IObserver%601.OnCompleted%2A> method, the `GetTemperature` method clears the <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="74056-128">공급자에 대 한 호출을 있게 하는 경우에 <xref:System.IObserver%601.OnError%2A> 해당 관찰자의 메서드.</span><span class="sxs-lookup"><span data-stu-id="74056-128">In this case, the provider makes no calls to the <xref:System.IObserver%601.OnError%2A> method of its observers.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#6)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="74056-129">예제</span><span class="sxs-lookup"><span data-stu-id="74056-129">Example</span></span>  
 <span data-ttu-id="74056-130">다음 예제에서는 포함을 정의 하기 위한 전체 소스 코드는 <xref:System.IObservable%601> 온도 모니터링 응용 프로그램에 대 한 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-130">The following example contains the complete source code for defining an <xref:System.IObservable%601> implementation for a temperature monitoring application.</span></span> <span data-ttu-id="74056-131">포함 된 `Temperature` 관찰자에 게 전송 되는 데이터 구조 및 `TemperatureMonitor` 클래스 즉는 <xref:System.IObservable%601> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="74056-131">It includes the `Temperature` structure, which is the data sent to observers, and the `TemperatureMonitor` class, which is the <xref:System.IObservable%601> implementation.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/provider.cs#7)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/provider.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="74056-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74056-132">See Also</span></span>  
 <xref:System.IObservable%601>  
 [<span data-ttu-id="74056-133">관찰자 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="74056-133">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="74056-134">방법: 관찰자 구현</span><span class="sxs-lookup"><span data-stu-id="74056-134">How to: Implement an Observer</span></span>](../../../docs/standard/events/how-to-implement-an-observer.md)  
 [<span data-ttu-id="74056-135">관찰자 디자인 패턴 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="74056-135">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
