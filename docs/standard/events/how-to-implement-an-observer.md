---
title: '방법: 관찰자 구현'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- observers [.NET Framework], observer design pattern
- observer design pattern [.NET Framework], implementing observers
ms.assetid: 8ecfa9f5-b500-473d-bcf0-5652ffb1e53d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f291bc91575ccde346f16552636d44951a0e6eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-implement-an-observer"></a><span data-ttu-id="85a33-102">방법: 관찰자 구현</span><span class="sxs-lookup"><span data-stu-id="85a33-102">How to: Implement an Observer</span></span>
<span data-ttu-id="85a33-103">관찰자 디자인 패턴은 알림에 등록하는 관찰자와 데이터를 모니터링하고 하나 이상의 관찰자에게 알림을 보내는 공급자 간에 구분이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-103">The observer design pattern requires a division between an observer, which registers for notifications, and a provider, which monitors data and sends notifications to one or more observers.</span></span> <span data-ttu-id="85a33-104">이 항목에서는 관찰자를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-104">This topic discusses how to create an observer.</span></span> <span data-ttu-id="85a33-105">관련 항목인 [방법: 공급자 구현](../../../docs/standard/events/how-to-implement-a-provider.md)에서는 공급자를 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-105">A related topic, [How to: Implement a Provider](../../../docs/standard/events/how-to-implement-a-provider.md), discusses how to create an provider.</span></span>  
  
### <a name="to-create-an-observer"></a><span data-ttu-id="85a33-106">관찰자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="85a33-106">To create an observer</span></span>  
  
1.  <span data-ttu-id="85a33-107"><xref:System.IObserver%601?displayProperty=nameWithType> 인터페이스를 구현하는 형식인 관찰자를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-107">Define the observer, which is a type that implements the <xref:System.IObserver%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="85a33-108">예를 들어 다음 코드에서는 `Temperature`의 제네릭 형식 인수를 사용하여 구성된 <xref:System.IObserver%601?displayProperty=nameWithType> 구현인 `TemperatureReporter`라는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-108">For example, the following code defines a type named `TemperatureReporter` that is a constructed <xref:System.IObserver%601?displayProperty=nameWithType> implementation with a generic type argument of `Temperature`.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#8)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#8)]  
  
2.  <span data-ttu-id="85a33-109">공급자가 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현을 호출하기 전에 관찰자가 알림 수신을 중지할 수 있는 경우 공급자의 <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> 메서드에서 반환한 <xref:System.IDisposable> 구현을 유지할 private 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-109">If the observer can stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, define a private variable that will hold the <xref:System.IDisposable> implementation returned by the provider's <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="85a33-110">또한 공급자의 <xref:System.IObservable%601.Subscribe%2A> 메서드를 호출하고 반환된 <xref:System.IDisposable> 개체를 저장하는 구독 메서드도 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-110">You should also define a subscription method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and stores the returned <xref:System.IDisposable> object.</span></span> <span data-ttu-id="85a33-111">예를 들어 다음 코드는 `unsubscriber`라는 private 변수를 정의하고, 공급자의 <xref:System.IObservable%601.Subscribe%2A> 메서드를 호출하고 반환된 개체를 `unsubscriber` 변수에 할당하는 `Subscribe` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-111">For example, the following code defines a private variable named `unsubscriber` and defines a `Subscribe` method that calls the provider's <xref:System.IObservable%601.Subscribe%2A> method and assigns the returned object to the `unsubscriber` variable.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#9)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#9)]  
  
3.  <span data-ttu-id="85a33-112">이 기능이 필수인 경우 공급자가 해당 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> 구현을 호출하기 전에 관찰자가 알림 수신을 중지할 수 있게 하는 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-112">Define a method that enables the observer to stop receiving notifications before the provider calls its <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType> implementation, if this feature is required.</span></span> <span data-ttu-id="85a33-113">다음 예제에서는 `Unsubscribe` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-113">The following example defines an `Unsubscribe` method.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#10)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#10)]  
  
4.  <span data-ttu-id="85a33-114"><xref:System.IObserver%601> 인터페이스로 정의된 세 가지 메서드 즉, <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType> 및 <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>의 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-114">Provide implementations of the three methods defined by the <xref:System.IObserver%601> interface: <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, and <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="85a33-115">공급자 및 응용 프로그램의 필요에 따라 <xref:System.IObserver%601.OnError%2A> 및 <xref:System.IObserver%601.OnCompleted%2A> 메서드가 스텁 구현일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-115">Depending on the provider and the needs of the application, the <xref:System.IObserver%601.OnError%2A> and <xref:System.IObserver%601.OnCompleted%2A> methods can be stub implementations.</span></span> <span data-ttu-id="85a33-116"><xref:System.IObserver%601.OnError%2A> 메서드는 전달된 <xref:System.Exception> 개체를 예외로 처리해서는 안 되며, <xref:System.IObserver%601.OnCompleted%2A> 메서드는 공급자의 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구현을 자유롭게 호출할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-116">Note that the <xref:System.IObserver%601.OnError%2A> method should not handle the passed <xref:System.Exception> object as an exception, and the <xref:System.IObserver%601.OnCompleted%2A> method is free to call the provider's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="85a33-117">다음 예제에서는 `TemperatureReporter` 클래스의 <xref:System.IObserver%601> 구현을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-117">The following example shows the <xref:System.IObserver%601> implementation of the `TemperatureReporter` class.</span></span>  
  
     [!code-csharp[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#11)]
     [!code-vb[Conceptual.ObserverDesign.HowTo#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="85a33-118">예</span><span class="sxs-lookup"><span data-stu-id="85a33-118">Example</span></span>  
 <span data-ttu-id="85a33-119">다음 예제에는 온도 모니터링 응용 프로그램에 대한 <xref:System.IObserver%601> 구현을 제공하는 `TemperatureReporter` 클래스의 전체 소스 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a33-119">The following example contains the complete source code for the `TemperatureReporter` class, which provides the <xref:System.IObserver%601> implementation for a temperature monitoring application.</span></span>  
  
 [!code-csharp[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesign.howto/cs/observer.cs#12)]
 [!code-vb[Conceptual.ObserverDesign.HowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesign.howto/vb/observer.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="85a33-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85a33-120">See Also</span></span>  
 <xref:System.IObserver%601>  
 [<span data-ttu-id="85a33-121">관찰자 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="85a33-121">Observer Design Pattern</span></span>](../../../docs/standard/events/observer-design-pattern.md)  
 [<span data-ttu-id="85a33-122">방법: 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="85a33-122">How to: Implement a Provider</span></span>](../../../docs/standard/events/how-to-implement-a-provider.md)  
 [<span data-ttu-id="85a33-123">관찰자 디자인 패턴 유용한 정보</span><span class="sxs-lookup"><span data-stu-id="85a33-123">Observer Design Pattern Best Practices</span></span>](../../../docs/standard/events/observer-design-pattern-best-practices.md)
