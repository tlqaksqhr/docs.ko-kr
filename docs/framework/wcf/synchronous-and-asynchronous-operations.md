---
title: "동기 및 비동기 작업"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], synchronous operations
- service contracts [WCF], asynchronous operations
ms.assetid: db8a51cb-67e6-411b-9035-e5821ed350c9
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fce4129924b4f0ce4542f2d274d2cc4031928c9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="synchronous-and-asynchronous-operations"></a><span data-ttu-id="c0fe4-102">동기 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="c0fe4-102">Synchronous and Asynchronous Operations</span></span>
<span data-ttu-id="c0fe4-103">이 항목에서는 비동기 서비스 작업의 구현 및 호출에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-103">This topic discusses implementing and calling asynchronous service operations.</span></span>  
  
 <span data-ttu-id="c0fe4-104">대부분의 응용 프로그램은 메서드를 비동기적으로 호출합니다. 이렇게 하면 메서드 호출이 실행되는 동안 응용 프로그램이 유용한 작업을 계속할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-104">Many applications call methods asynchronously because it enables the application to continue doing useful work while the method call runs.</span></span> [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="c0fe4-105"> 서비스와 클라이언트는 두 개의 다른 응용 프로그램 수준에서 비동기 작업 호출에 참여할 수 있으므로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램에서 보다 유연하게 상호 작용과 균형을 맞춰 처리량을 최대화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-105"> services and clients can participate in asynchronous operation calls at two distinct levels of the application, which provide [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications even more flexibility to maximize throughput balanced against interactivity.</span></span>  
  
## <a name="types-of-asynchronous-operations"></a><span data-ttu-id="c0fe4-106">비동기 작업 형식</span><span class="sxs-lookup"><span data-stu-id="c0fe4-106">Types of Asynchronous Operations</span></span>  
 <span data-ttu-id="c0fe4-107">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 모든 서비스 계약은 매개 변수 형식 및 반환 값에 관계없이 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 특성을 사용하여 클라이언트와 서비스 간의 특정 메시지 교환 패턴을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-107">All service contracts in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], no matter the parameters types and return values, use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] attributes to specify a particular message exchange pattern between client and service.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="c0fe4-108">에서는 인바운드 및 아웃바운드 메시지를 자동으로 적절한 서비스 작업이나 실행 중인 클라이언트 코드로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-108"> automatically routes inbound and outbound messages to the appropriate service operation or running client code.</span></span>  
  
 <span data-ttu-id="c0fe4-109">클라이언트는 특정 작업의 메시지 교환 패턴을 지정하는 서비스 계약만 소유하며</span><span class="sxs-lookup"><span data-stu-id="c0fe4-109">The client possesses only the service contract, which specifies the message exchange pattern for a particular operation.</span></span> <span data-ttu-id="c0fe4-110">기본 메시지 교환 패턴이 확인되는 한 클라이언트가 선택한 프로그래밍 모델을 개발자에게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-110">Clients can offer the developer any programming model they choose, so long as the underlying message exchange pattern is observed.</span></span> <span data-ttu-id="c0fe4-111">또한 지정된 메시지 패턴이 확인되는 한 서비스도 임의의 방식으로 작업을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-111">So, too, can services implement operations in any manner, so long as the specified message pattern is observed.</span></span>  
  
 <span data-ttu-id="c0fe4-112">서비스나 클라이언트 구현에서 서비스 계약이 독립되면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램에서 다음과 같은 비동기 실행을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-112">The independence of the service contract from either the service or client implementation enables the following forms of asynchronous execution in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications:</span></span>  
  
-   <span data-ttu-id="c0fe4-113">클라이언트는 동기 메시지 교환을 사용하여 요청/응답 작업을 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-113">Clients can invoke request/response operations asynchronously using a synchronous message exchange.</span></span>  
  
-   <span data-ttu-id="c0fe4-114">서비스는 동기 메시지 교환을 사용하여 요청/응답 작업을 비동기적으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-114">Services can implement a request/response operation asynchronously using a synchronous message exchange.</span></span>  
  
-   <span data-ttu-id="c0fe4-115">클라이언트나 서비스의 구현에 관계없이 메시지 교환은 단방향일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-115">Message exchanges can be one-way, regardless of the implementation of the client or service.</span></span>  
  
### <a name="suggested-asynchronous-scenarios"></a><span data-ttu-id="c0fe4-116">제안된 비동기 시나리오</span><span class="sxs-lookup"><span data-stu-id="c0fe4-116">Suggested Asynchronous Scenarios</span></span>  
 <span data-ttu-id="c0fe4-117">작업 서비스 구현에서 I/O 작업을 수행하는 경우와 같이 블로킹 호출을 만드는 경우 서비스 작업 구현에서 비동기 접근 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-117">Use an asynchronous approach in a service operation implementation if the operation service implementation makes a blocking call, such as doing I/O work.</span></span> <span data-ttu-id="c0fe4-118">비동기 작업 구현 중인 경우에는 비동기 작업 및 메서드를 호출하여 비동기 호출 경로를 최대한 확장해 보세요.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-118">When you are in an asynchronous operation implementation, try to call asynchronous operations and methods to extend the asynchronous call path as far as possible.</span></span> <span data-ttu-id="c0fe4-119">예를 들면 `BeginOperationTwo()` 내에서 `BeginOperationOne()`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-119">For example, call a `BeginOperationTwo()` from within `BeginOperationOne()`.</span></span>  
  
-   <span data-ttu-id="c0fe4-120">다음과 같은 경우에는 클라이언트 또는 호출 응용 프로그램에서 비동기 접근 방법을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-120">Use an asynchronous approach in a client or calling application in the following cases:</span></span>  
  
-   <span data-ttu-id="c0fe4-121">중간 계층 응용 프로그램에서 작업을 호출하는 경우.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-121">If you are invoking operations from a middle-tier application.</span></span> <span data-ttu-id="c0fe4-122">([!INCLUDE[crabout](../../../includes/crabout-md.md)] 이러한 시나리오 참조 [중간 계층 클라이언트 응용 프로그램](../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).)</span><span class="sxs-lookup"><span data-stu-id="c0fe4-122">([!INCLUDE[crabout](../../../includes/crabout-md.md)] such scenarios, see [Middle-Tier Client Applications](../../../docs/framework/wcf/feature-details/middle-tier-client-applications.md).)</span></span>  
  
-   <span data-ttu-id="c0fe4-123">ASP.NET 페이지 내에서 작업을 호출하는 경우에는 비동기 페이지를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-123">If you are invoking operations within an ASP.NET page, use asynchronous pages.</span></span>  
  
-   <span data-ttu-id="c0fe4-124">Windows Forms 또는 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] 등의 단일 스레드 응용 프로그램에서 작업을 호출하는 경우.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-124">If you are invoking operations from any application that is single threaded, such as Windows Forms or [!INCLUDE[avalon1](../../../includes/avalon1-md.md)].</span></span> <span data-ttu-id="c0fe4-125">이벤트 기반의 비동기 호출 모델을 사용하는 경우에는 결과 이벤트가 UI 스레드에서 발생하기 때문에 사용자가 직접 여러 스레드를 처리할 필요 없이 응용 프로그램에 응답이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-125">When using the event-based asynchronous calling model, the result event is raised on the UI thread, adding responsiveness to the application without requiring you to handle multiple threads yourself.</span></span>  
  
-   <span data-ttu-id="c0fe4-126">일반적으로 동기 호출과 비동기 호출 중에서 선택해야 하는 경우에는 비동기 호출을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-126">In general, if you have a choice between a synchronous and asynchronous call, choose the asynchronous call.</span></span>  
  
### <a name="implementing-an-asynchronous-service-operation"></a><span data-ttu-id="c0fe4-127">비동기 서비스 작업 구현</span><span class="sxs-lookup"><span data-stu-id="c0fe4-127">Implementing an Asynchronous Service Operation</span></span>  
 <span data-ttu-id="c0fe4-128">다음 세 가지 방법 중 하나를 사용하여 비동기 작업을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-128">Asynchronous operations can be implemented by using one of the three following methods:</span></span>  
  
1.  <span data-ttu-id="c0fe4-129">작업 기반 비동기 패턴</span><span class="sxs-lookup"><span data-stu-id="c0fe4-129">The task-based asynchronous pattern</span></span>  
  
2.  <span data-ttu-id="c0fe4-130">이벤트 기반 비동기 패턴</span><span class="sxs-lookup"><span data-stu-id="c0fe4-130">The event-based asynchronous pattern</span></span>  
  
3.  <span data-ttu-id="c0fe4-131">IAsyncResult 비동기 패턴</span><span class="sxs-lookup"><span data-stu-id="c0fe4-131">The IAsyncResult asynchronous pattern</span></span>  
  
#### <a name="task-based-asynchronous-pattern"></a><span data-ttu-id="c0fe4-132">작업 기반 비동기 패턴</span><span class="sxs-lookup"><span data-stu-id="c0fe4-132">Task-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="c0fe4-133">작업 기반 비동기 패턴은 가장 쉽고 단순하기 때문에 비동기 작업을 구현하는 데 가장 선호하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-133">The task-based asynchronous pattern is the preferred way to implement asynchronous operations because it is the easiest and most straight forward.</span></span> <span data-ttu-id="c0fe4-134">이 방법을 사용 하려면 서비스 작업을 구현 하 고 작업의 반환 형식을 지정\<T >, 여기서 T는 논리 연산에서 반환 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-134">To use this method simply implement your service operation and specify a return type of Task\<T>, where T is the type returned by the logical operation.</span></span> <span data-ttu-id="c0fe4-135">예:</span><span class="sxs-lookup"><span data-stu-id="c0fe4-135">For example:</span></span>  
  
```csharp  
public class SampleService:ISampleService   
{   
   // ...  
   public async Task<string> SampleMethodTaskAsync(string msg)   
   {   
      return Task<string>.Factory.StartNew(() =>   
      {   
         return msg;   
      });   
   }  
   // ...  
}  
```  
  
 <span data-ttu-id="c0fe4-136">SampleMethodTaskAsync 작업은 반환\<문자열 > 문자열을 반환 하는 논리 연산 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-136">The SampleMethodTaskAsync operation returns Task\<string> because the logical operation returns a string.</span></span> <span data-ttu-id="c0fe4-137">작업 기반 비동기 패턴에 대 한 자세한 내용은 참조 [작업 기반 비동기 패턴](http://go.microsoft.com/fwlink/?LinkId=232504)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-137">For more information about the task-based asynchronous pattern, see [The Task-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=232504).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c0fe4-138">작업 기반 비동기 패턴을 사용할 경우 작업 완료를 대기하는 동안 예외가 발생하면 T:System.AggregateException이 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-138">When using the task-based asynchronous pattern, a T:System.AggregateException may be thrown if an exception occurs while waiting on the completion of the operation.</span></span> <span data-ttu-id="c0fe4-139">클라이언트 또는 서비스에서 이 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-139">This exception may occur on the client or services</span></span>  
  
#### <a name="event-based-asynchronous-pattern"></a><span data-ttu-id="c0fe4-140">이벤트 기반 비동기 패턴</span><span class="sxs-lookup"><span data-stu-id="c0fe4-140">Event-Based Asynchronous Pattern</span></span>  
 <span data-ttu-id="c0fe4-141">이벤트 기반 비동기 패턴을 지원하는 서비스에는 MethodNameAsync라는 작업이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-141">A service that supports the Event-based Asynchronous Pattern will have one or more operations named MethodNameAsync.</span></span> <span data-ttu-id="c0fe4-142">이러한 메서드는 현재 스레드에서 동일한 작업을 수행하는 동기 버전을 미러링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-142">These methods may mirror synchronous versions, which perform the same operation on the current thread.</span></span> <span data-ttu-id="c0fe4-143">또한 이 클래스에는 MethodNameCompleted 이벤트가 있을 수 있고 MethodNameAsyncCancel 메서드가 있거나 단순히 CancelAsync 메서드가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-143">The class may also have a MethodNameCompleted event and it may have a MethodNameAsyncCancel (or simply CancelAsync) method.</span></span> <span data-ttu-id="c0fe4-144">작업을 호출하려는 클라이언트는 작업이 완료될 때 호출할 이벤트 처리기를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-144">A client wishing to call the operation will define an event handler to be called when the operation completes,</span></span>  
  
 <span data-ttu-id="c0fe4-145">다음 코드 조각에서는 이벤트 기반 비동기 패턴을 사용하여 비동기 작업을 선언하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-145">The following code snippet illustrates how to declare asynchronous operations using the event-based asynchronous pattern.</span></span>  
  
```csharp  
public class AsyncExample  
{  
    // Synchronous methods.  
    public int Method1(string param);  
    public void Method2(double param);  
  
    // Asynchronous methods.  
    public void Method1Async(string param);  
    public void Method1Async(string param, object userState);  
    public event Method1CompletedEventHandler Method1Completed;  
  
    public void Method2Async(double param);  
    public void Method2Async(double param, object userState);  
    public event Method2CompletedEventHandler Method2Completed;  
  
    public void CancelAsync(object userState);  
  
    public bool IsBusy { get; }  
  
    // Class implementation not shown.  
}  
```  
  
 <span data-ttu-id="c0fe4-146">이벤트 기반 비동기 패턴에 대 한 자세한 내용은 참조 [이벤트 기반 비동기 패턴](http://go.microsoft.com/fwlink/?LinkId=232515)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-146">For more information about the Event-based Asynchronous Pattern, see [The Event-Based Asynchronous Pattern](http://go.microsoft.com/fwlink/?LinkId=232515).</span></span>  
  
#### <a name="iasyncresult-asynchronous-pattern"></a><span data-ttu-id="c0fe4-147">IAsyncResult 비동기 패턴</span><span class="sxs-lookup"><span data-stu-id="c0fe4-147">IAsyncResult Asynchronous Pattern</span></span>  
 <span data-ttu-id="c0fe4-148">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 비동기 프로그래밍 패턴을 사용하고 `<Begin>` 속성이 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>로 설정된 `true` 메서드를 표시하여 서비스 작업을 비동기 방식으로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-148">A service operation can be implemented in an asynchronous fashion using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] asynchronous programming pattern and marking the `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true`.</span></span> <span data-ttu-id="c0fe4-149">이 경우 비동기 작업은 동기 작업과 동일한 형태로 메타데이터에 노출됩니다. 즉, 요청 메시지와 관련 응답 메시지가 포함된 단일 작업으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-149">In this case, the asynchronous operation is exposed in metadata in the same form as a synchronous operation: It is exposed as a single operation with a request message and a correlated response message.</span></span> <span data-ttu-id="c0fe4-150">그런 다음 클라이언트 프로그래밍 모델에서는 둘 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-150">Client programming models then have a choice.</span></span> <span data-ttu-id="c0fe4-151">즉, 서비스가 호출될 때 요청-응답 메시지 교환이 발생하는 한 이 패턴을 동기 작업이나 비동기 작업으로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-151">They can represent this pattern as a synchronous operation or as an asynchronous one, so long as when the service is invoked a request-response message exchange takes place.</span></span>  
  
 <span data-ttu-id="c0fe4-152">일반적으로 시스템의 비동기 특성을 사용하는 경우 스레드에 대한 종속성을 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-152">In general, with the asynchronous nature of the systems, you should not take a dependency on the threads.</span></span>  <span data-ttu-id="c0fe4-153">작업 디스패치 처리의 다양한 단계에 데이터를 전달하는 가장 안정적인 방법은 확장을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-153">The most reliable way of passing data to various stages of operation dispatch processing is to use extensions.</span></span>  
  
 <span data-ttu-id="c0fe4-154">예를 들어 참조 [하는 방법: 비동기 서비스 작업 구현](../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-154">For an example, see [How to: Implement an Asynchronous Service Operation](../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span>  
  
 <span data-ttu-id="c0fe4-155">클라이언트 응용 프로그램에서 호출되는 방식에 관계없이 비동기적으로 실행되는 계약 작업 `X`를 정의하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-155">To define a contract operation `X` that is executed asynchronously regardless of how it is called in the client application:</span></span>  
  
-   <span data-ttu-id="c0fe4-156">패턴 `BeginOperation` 및 `EndOperation`을 사용하여 두 개의 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-156">Define two methods using the pattern `BeginOperation` and `EndOperation`.</span></span>  
  
-   <span data-ttu-id="c0fe4-157">`BeginOperation` 메서드는 작업에 대한 `in` 및 `ref` 매개 변수를 포함하고 <xref:System.IAsyncResult> 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-157">The `BeginOperation` method includes `in` and `ref` parameters for the operation and returns an <xref:System.IAsyncResult> type.</span></span>  
  
-   <span data-ttu-id="c0fe4-158">`EndOperation` 메서드는 <xref:System.IAsyncResult> 및 `out` 매개 변수뿐 아니라 `ref` 매개 변수를 포함하고 작업 반환 형식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-158">The `EndOperation` method includes an <xref:System.IAsyncResult> parameter as well as the `out` and `ref` parameters and returns the operations return type.</span></span>  
  
 <span data-ttu-id="c0fe4-159">다음 메서드를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-159">For example, see the following method.</span></span>  
  
```csharp  
int DoWork(string data, ref string inout, out string outonly)  
```  
  
```vb  
Function DoWork(ByVal data As String, ByRef inout As String, _out outonly As out) As Integer  
```  
  
 <span data-ttu-id="c0fe4-160">비동기 작업을 만들려는 경우 두 가지 메서드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-160">To create an asynchronous operation, the two methods would be:</span></span>  
  
```csharp  
[OperationContract(AsyncPattern=true)]IAsyncResult BeginDoWork(string data,                           ref string inout,                           AsyncCallback callback,                           object state);int EndDoWork(ref string inout, out string outonly, IAsyncResult result);  
```  
  
```vb  
<OperationContract(AsyncPattern := True)>  _Function BeginDoWork(ByVal data As String, _                 ByRef inout As String, _                 ByVal callback As AsyncCallback, _                 ByVal state As Object) _As IAsyncResult Function EndDoWork(ByRef inout As String, _        ByRef outonly As String, _        ByVal result As IAsyncResult) _As Integer  
```  
  
> [!NOTE]
>  <span data-ttu-id="c0fe4-161"><xref:System.ServiceModel.OperationContractAttribute> 특성은 `BeginDoWork` 메서드에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-161">The <xref:System.ServiceModel.OperationContractAttribute> attribute is applied only to the `BeginDoWork` method.</span></span> <span data-ttu-id="c0fe4-162">결과 계약에는 `DoWork`라는 하나의 WSDL 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-162">The resulting contract has one WSDL operation named `DoWork`.</span></span>  
  
### <a name="client-side-asynchronous-invocations"></a><span data-ttu-id="c0fe4-163">클라이언트측 비동기 호출</span><span class="sxs-lookup"><span data-stu-id="c0fe4-163">Client-Side Asynchronous Invocations</span></span>  
 <span data-ttu-id="c0fe4-164">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 응용 프로그램은 위에서 설명한 세 가지 비동기 호출 모델 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-164">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client application can use any of three asynchronous calling models described previously</span></span>  
  
 <span data-ttu-id="c0fe4-165">작업 기반 모델을 사용하는 경우 다음 코드 조각과 같이 await 키워드를 사용하여 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-165">When using the task-based model, simply call the operation using the await keyword as shown in the following code snippet.</span></span>  
  
```  
await simpleServiceClient.SampleMethodTaskAsync("hello, world");  
```  
  
 <span data-ttu-id="c0fe4-166">이벤트 기반 비동기 패턴을 사용할 경우 응답 알림을 받기 위해 이벤트 처리기를 추가하기만 하면 되고 결과 이벤트가 사용자 인터페이스 스레드에서 자동으로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-166">Using the event-based asynchronous pattern only requires adding an event handler to receive a notification of the response -- and the resulting event is raised on the user interface thread automatically.</span></span> <span data-ttu-id="c0fe4-167">이 방법을 사용 하려면 둘 다 지정는 **/async** 및 **/tcv:Version35** 명령 옵션으로는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)와 같이, 다음 예입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-167">To use this approach, specify both the **/async** and **/tcv:Version35** command options with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async /tcv:Version35  
```  
  
 <span data-ttu-id="c0fe4-168">그러면 Svcutil.exe는 호출 응용 프로그램이 응답을 받고 적절한 작업을 수행하기 위한 이벤트 처리기를 구현하고 할당할 수 있는 이벤트 인프라를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-168">When this is done, Svcutil.exe generates a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client class with the event infrastructure that enables the calling application to implement and assign an event handler to receive the response and take the appropriate action.</span></span> <span data-ttu-id="c0fe4-169">전체 예제를 참조 하십시오. [하는 방법: 비동기적 서비스 작업 호출](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-169">For a complete example, see [How to: Call Service Operations Asynchronously](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
 <span data-ttu-id="c0fe4-170">그러나 이벤트 기반 비동기 모델은 [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)]에서만 사용할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="c0fe4-170">The event-based asynchronous model, however, is only available in [!INCLUDE[netfx35_long](../../../includes/netfx35-long-md.md)].</span></span> <span data-ttu-id="c0fe4-171">[!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 채널이 만들어진 경우에는 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>에서도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-171">In addition, it is not supported even in [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] when a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client channel is created by using a <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="c0fe4-172">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 채널 개체가 있는 경우 <xref:System.IAsyncResult?displayProperty=nameWithType> 개체를 사용하여 작업을 비동기적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-172">With [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client channel objects, you must use <xref:System.IAsyncResult?displayProperty=nameWithType> objects to invoke your operations asynchronously.</span></span> <span data-ttu-id="c0fe4-173">이 방법을 사용 하려면 지정 된 **/async** 명령 옵션으로는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)다음 예제와 같이, 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-173">To use this approach, specify the **/async** command option with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), as in the following example.</span></span>  
  
```  
svcutil http://localhost:8000/servicemodelsamples/service/mex /async   
```  
  
 <span data-ttu-id="c0fe4-174">그러면 각 작업이 `<Begin>` 속성이 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>로 설정된 `true` 메서드와 해당 `<End>` 메서드로 모델링되는 서비스 계약이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-174">This generates a service contract in which each operation is modeled as a `<Begin>` method with the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A> property set to `true` and a corresponding `<End>` method.</span></span> <span data-ttu-id="c0fe4-175">사용 하 여 전체 예제는 <xref:System.ServiceModel.ChannelFactory%601>, 참조 [하는 방법: 호출 작업이 비동기적으로 사용 하 여 채널 팩터리](../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-175">For a complete example using a <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
 <span data-ttu-id="c0fe4-176">두 경우 모두 응용 프로그램은 서비스가 동기적으로 구현되더라도 동일한 패턴을 사용하여 로컬 동기 메서드를 비동기적으로 호출하는 것과 같은 방식으로 작업을 비동기적으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-176">In either case, applications can invoke an operation asynchronously even if the service is implemented synchronously, in the same way that an application can use the same pattern to invoke asynchronously a local synchronous method.</span></span> <span data-ttu-id="c0fe4-177">작업이 구현되는 방식은 클라이언트에게 중요하지 않습니다. 응답 메시지가 도착하면 메시지 내용이 클라이언트의 비동기 <`End`> 메서드에 디스패치되고 클라이언트는 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-177">How the operation is implemented is not significant to the client; when the response message arrives, its content is dispatched to the client's asynchronous <`End`> method and the client retrieves the information.</span></span>  
  
### <a name="one-way-message-exchange-patterns"></a><span data-ttu-id="c0fe4-178">단방향 메시지 교환 패턴</span><span class="sxs-lookup"><span data-stu-id="c0fe4-178">One-Way Message Exchange Patterns</span></span>  
 <span data-ttu-id="c0fe4-179">클라이언트 또는 서비스에서 단독으로 어느 방향으로나 단방향 작업(<xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType>가 `true`인 작업에는 관련 응답이 없음)을 보낼 수 있는 비동기 메시지 교환 패턴을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-179">You can also create an asynchronous message exchange pattern in which one-way operations (operations for which the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A?displayProperty=nameWithType> is `true` have no correlated response) can be sent in either direction by the client or service independently of the other side.</span></span> <span data-ttu-id="c0fe4-180">이 메시지 교환 패턴에서는 단방향 메시지에 이중 메시지 교환 패턴을 사용합니다. 이 경우 서비스 계약은 어느 쪽에서든 필요에 따라 적절하게 비동기 호출 또는 구현으로 구현할 수 있는 단방향 메시지 교환을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-180">(This uses the duplex message exchange pattern with one-way messages.) In this case, the service contract specifies a one-way message exchange that either side can implement as asynchronous calls or implementations, or not, as appropriate.</span></span> <span data-ttu-id="c0fe4-181">일반적으로 계약이 단방향 메시지 교환이면 메시지가 전송된 후 응용 프로그램이 응답을 기다리지 않고 계속해서 다른 작업을 수행할 수 있으므로 구현이 대체로 비동기적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-181">Generally, when the contract is an exchange of one-way messages, the implementations can largely be asynchronous because once a message is sent the application does not wait for a reply and can continue doing other work.</span></span>  
  
### <a name="event-based-asynchronous-clients-and-message-contracts"></a><span data-ttu-id="c0fe4-182">이벤트 기반 비동기 클라이언트 및 메시지 계약</span><span class="sxs-lookup"><span data-stu-id="c0fe4-182">Event-based Asynchronous Clients and Message Contracts</span></span>  
 <span data-ttu-id="c0fe4-183">이벤트 기반 비동기 모델에 대한 디자인 지침에 따르면 둘 이상의 값이 반환될 경우 그 중 하나는 `Result` 속성으로 반환되고 나머지 값은 <xref:System.EventArgs> 개체의 속성으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-183">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="c0fe4-184">따라서 클라이언트가 이벤트 기반 비동기 명령 옵션을 사용하여 메타데이터를 가져오고 작업이 둘 이상의 값을 반환할 경우 기본 <xref:System.EventArgs> 개체는 그 중 하나를 `Result` 속성으로 반환하고, 나머지 값은 <xref:System.EventArgs> 개체의 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-184">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="c0fe4-185">으로 메시지 개체를 수신 하려는 경우는 `Result` 속성 하 고 해당 개체의 속성을 사용 하 여 반환 된 값을 가지는 **/messageContract** 명령 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-185">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the **/messageContract** command option.</span></span> <span data-ttu-id="c0fe4-186">이렇게 하면 응답 메시지를 `Result` 개체의 <xref:System.EventArgs> 속성으로 반환하는 서명이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-186">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="c0fe4-187">모든 내부 반환 값은 응답 메시지 개체의 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fe4-187">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fe4-188">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0fe4-188">See Also</span></span>  
 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>  
 <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A>
