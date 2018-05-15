---
title: 사용자 지정 수명
ms.date: 03/30/2017
ms.assetid: 52806c07-b91c-48fe-b992-88a41924f51f
ms.openlocfilehash: e41c970739b8036730fa601433ce7157e01d7e19
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="custom-lifetime"></a><span data-ttu-id="8c0d4-102">사용자 지정 수명</span><span class="sxs-lookup"><span data-stu-id="8c0d4-102">Custom Lifetime</span></span>
<span data-ttu-id="8c0d4-103">이 샘플에는 WCF 서비스 인스턴스를 공유에 대 한 사용자 지정 수명 서비스를 제공 하는 Windows Communication Foundation (WCF) 확장을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-103">This sample demonstrates how to write a Windows Communication Foundation (WCF) extension to provide custom lifetime services for shared WCF service instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8c0d4-104">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="shared-instancing"></a><span data-ttu-id="8c0d4-105">공유 인스턴스 만들기</span><span class="sxs-lookup"><span data-stu-id="8c0d4-105">Shared Instancing</span></span>  
 <span data-ttu-id="8c0d4-106">WCF는 서비스 인스턴스에 대 한 인스턴스 만들기 모드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-106">WCF offers several instancing modes for your service instances.</span></span> <span data-ttu-id="8c0d4-107">이 항목에서 설명하는 공유 인스턴스 만들기 모드를 사용하면 여러 채널 간에 서비스 인스턴스를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-107">The Shared Instancing mode covered in this topic provides a way to share a service instance between multiple channels.</span></span> <span data-ttu-id="8c0d4-108">클라이언트에서는 인스턴스의 끝점 주소를 로컬로 확인하거나 서비스의 팩터리 메서드에 연결하여 실행 중인 인스턴스의 끝점 주소를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-108">Clients can either resolve the instance’s endpoint address locally or contact a factory method in the service to obtain the endpoint address of a running instance.</span></span> <span data-ttu-id="8c0d4-109">끝점 주소를 가져온 후에는 새 채널을 만들고 통신을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-109">Once it has the endpoint address, it can create a new channel and start communication.</span></span> <span data-ttu-id="8c0d4-110">다음 코드 조각에서는 클라이언트 응용 프로그램에서 기존 서비스 인스턴스에 대한 새 채널을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-110">The following code snippet shows how a client application creates a new channel to an existing service instance.</span></span>  
  
```  
// Create the first channel.  
IEchoService proxy = channelFactory.CreateChannel();  
  
// Resolve the instance.  
EndpointAddress epa = ((IClientChannel)proxy).ResolveInstance();  
  
// Create new channel factory with the endpoint address resolved by   
// previous statement.  
ChannelFactory<IEchoService> channelFactory2 =  
                new ChannelFactory<IEchoService>("echoservice",  
                epa);  
  
// Create the second channel to the same instance.  
IEchoService proxy2 = channelFactory2.CreateChannel();  
```  
  
 <span data-ttu-id="8c0d4-111">다른 인스턴스 만들기 모드와 달리 공유 인스턴스 만들기 모드에는 서비스 인스턴스를 해제하는 고유한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-111">Unlike other instancing modes, the shared instancing mode has a unique way of releasing the service instances.</span></span> <span data-ttu-id="8c0d4-112">인스턴스에 대 한 모든 채널이 닫히면 서비스 WCF 런타임 타이머를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-112">When all the channels are closed for an instance, the service WCF runtime starts a timer.</span></span> <span data-ttu-id="8c0d4-113">제한 시간이 만료 되기 전에 아무도 연결, WCF의 인스턴스를 해제 하 고 리소스를 확보 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-113">If nobody makes a connection before the timeout expires, WCF releases the instance and claims the resources.</span></span> <span data-ttu-id="8c0d4-114">중지 절차의 일부로 WCF 호출는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 모든 메서드 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 인스턴스를 해제 하기 전에 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-114">As a part of the teardown procedure WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of all <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementations before releasing the instance.</span></span> <span data-ttu-id="8c0d4-115">모든 메서드가 `true`를 반환하면 인스턴스가 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-115">If all of them return `true` the instance is released.</span></span> <span data-ttu-id="8c0d4-116">그렇지 않으면 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현에서 콜백 메서드를 사용하여 `Dispatcher`에 유휴 상태를 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-116">Otherwise the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is responsible for notifying the `Dispatcher` of the idle state by using a callback method.</span></span>  
  
 <span data-ttu-id="8c0d4-117">기본적으로 <xref:System.ServiceModel.InstanceContext>의 유휴 제한 시간 값은 1분입니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-117">By default, the idle timeout value of <xref:System.ServiceModel.InstanceContext> is one minute.</span></span> <span data-ttu-id="8c0d4-118">그러나 이 샘플에서는 사용자 지정 확장을 사용하여 이 시간을 연장하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-118">However this sample demonstrates how you can extend this using a custom extension.</span></span>  
  
## <a name="extending-the-instancecontext"></a><span data-ttu-id="8c0d4-119">InstanceContext 확장</span><span class="sxs-lookup"><span data-stu-id="8c0d4-119">Extending the InstanceContext</span></span>  
 <span data-ttu-id="8c0d4-120">Wcf에서는 <xref:System.ServiceModel.InstanceContext> 은 서비스 인스턴스 사이의 연결 및 `Dispatcher`합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-120">In WCF, <xref:System.ServiceModel.InstanceContext> is the link between the service instance and the `Dispatcher`.</span></span> <span data-ttu-id="8c0d4-121">WCF를 사용 하면 확장 가능한 개체 패턴을 사용 하 여 새 상태나 동작을 추가 하 여이 런타임 구성 요소를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-121">WCF allows you to extend this runtime component by adding new state or behavior by using its extensible object pattern.</span></span> <span data-ttu-id="8c0d4-122">확장명 가능한 개체 패턴은 새 기능으로 기존 런타임 클래스를 확장 하거나 하거나 개체에 새 상태 기능을 추가 하려면 WCF에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-122">The extensible object pattern is used in WCF to either extend existing runtime classes with new functionality or to add new state features to an object.</span></span> <span data-ttu-id="8c0d4-123">확장 가능한 개체 패턴에는 세 가지 인터페이스인 `IExtensibleObject<T>`, `IExtension<T>` 및 `IExtensionCollection<T>`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-123">There are three interfaces in the extensible object pattern: `IExtensibleObject<T>`, `IExtension<T>`, and `IExtensionCollection<T>`.</span></span>  
  
 <span data-ttu-id="8c0d4-124">`IExtensibleObject<T>` 인터페이스는 개체의 기능을 사용자 지정하는 확장을 허용하는 개체를 통해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-124">The `IExtensibleObject<T>` interface is implemented by objects to allow extensions which customize their functionality.</span></span>  
  
 <span data-ttu-id="8c0d4-125">`IExtension<T>` 인터페이스는 `T` 형식의 클래스 확장일 수 있는 개체에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-125">The `IExtension<T>` interface is implemented by objects that can be extensions of classes of type `T`.</span></span>  
  
 <span data-ttu-id="8c0d4-126">마지막으로, `IExtensionCollection<T>` 인터페이스는 형식별로 `IExtensions`를 검색할 수 있게 해 주는 `IExtensions`의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-126">And finally, the `IExtensionCollection<T>` interface is a collection of `IExtensions` that allows for retrieving `IExtensions` by their type.</span></span>  
  
 <span data-ttu-id="8c0d4-127">따라서 <xref:System.ServiceModel.InstanceContext>를 확장하려면 `IExtension` 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-127">Therefore in order to extend the <xref:System.ServiceModel.InstanceContext> you must implement the `IExtension` interface.</span></span> <span data-ttu-id="8c0d4-128">이 샘플 프로젝트에는 `CustomLeaseExtension` 클래스에 이 구현이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-128">In this sample project the `CustomLeaseExtension` class contains this implementation.</span></span>  
  
```  
class CustomLeaseExtension : IExtension<InstanceContext>  
{  
}  
```  
  
 <span data-ttu-id="8c0d4-129">`IExtension` 인터페이스에는 `Attach` 및 `Detach`의 두 가지 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-129">The `IExtension` interface has two methods `Attach` and `Detach`.</span></span> <span data-ttu-id="8c0d4-130">이름이 나타내듯이 이 두 메서드는 런타임에서 <xref:System.ServiceModel.InstanceContext> 클래스와 확장을 연결하거나 분리할 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-130">As their names imply, these two methods are called when the runtime attaches and detaches the extension to an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="8c0d4-131">이 샘플에서는 `Attach` 메서드를 사용하여 확장의 현재 인스턴스에 속한 <xref:System.ServiceModel.InstanceContext> 개체를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-131">In this sample, the `Attach` method is used to keep track of the <xref:System.ServiceModel.InstanceContext> object that belongs to the current instance of the extension.</span></span>  
  
```  
InstanceContext owner;  
  
public void Attach(InstanceContext owner)  
{  
  this.owner = owner;   
}  
```  
  
 <span data-ttu-id="8c0d4-132">또한 확장에 필요한 구현을 추가하여 연장된 수명 지원을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-132">In addition, you must add the necessary implementation to the extension to provide the extended lifetime support.</span></span> <span data-ttu-id="8c0d4-133">따라서 `ICustomLease` 인스턴스는 원하는 메서드로 선언되고 `CustomLeaseExtension` 클래스에서 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-133">Therefore the `ICustomLease` interface is declared with the desired methods and is implemented in the `CustomLeaseExtension` class.</span></span>  
  
```  
interface ICustomLease  
{  
    bool IsIdle { get; }          
    InstanceContextIdleCallback Callback { get; set; }  
}  
  
class CustomLeaseExtension : IExtension<InstanceContext>, ICustomLease  
{  
}  
```  
  
 <span data-ttu-id="8c0d4-134">WCF 호출 하는 경우는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 에서 메서드는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현이이 호출에 전달 되는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 의 메서드는 `CustomLeaseExtension`합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-134">When WCF invokes the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method in the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation this call is routed to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method of the `CustomLeaseExtension`.</span></span> <span data-ttu-id="8c0d4-135">그런 다음 `CustomLeaseExtension`에서 메서드의 전용 상태를 검사하여 <xref:System.ServiceModel.InstanceContext>가 유휴 상태인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-135">Then the `CustomLeaseExtension` checks its private state to see whether the <xref:System.ServiceModel.InstanceContext> is idle.</span></span> <span data-ttu-id="8c0d4-136">유휴 상태이면 이 메서드는 `true`를 반환하며,</span><span class="sxs-lookup"><span data-stu-id="8c0d4-136">If it is idle it returns `true`.</span></span> <span data-ttu-id="8c0d4-137">그렇지 않으면 연장된 수명 기간에 대한 타이머를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-137">Otherwise, it starts a timer for a specified amount of extended lifetime.</span></span>  
  
```  
public bool IsIdle  
{  
  get  
  {  
    lock (thisLock)  
    {  
      if (isIdle)  
      {  
        return true;  
      }  
      else  
      {  
        StartTimer();  
        return false;  
      }  
    }  
  }  
}  
```  
  
 <span data-ttu-id="8c0d4-138">타이머의 `Elapsed` 이벤트에서는 다른 정리 주기를 시작하기 위해 디스패처의 콜백 함수가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-138">In the timer’s `Elapsed` event the callback function in the Dispatcher is called in order to start another clean up cycle.</span></span>  
  
```  
void idleTimer_Elapsed(object sender, ElapsedEventArgs args)  
{  
    idleTimer.Stop();  
    isIdle = true;    
    callback(owner);  
}  
```  
  
 <span data-ttu-id="8c0d4-139">유휴 상태로 전환되는 인스턴스에 대해 새 메시지가 도착할 경우에는 실행 중인 타이머를 갱신할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-139">There is no way to renew the running timer when a new message arrives for the instance being moved to the idle state.</span></span>  
  
 <span data-ttu-id="8c0d4-140">이 샘플에서는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider>을 구현하여 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드에 대한 호출을 가로채고 이를 `CustomLeaseExtension`에 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-140">The sample implements <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> to intercept the calls to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method and route them to the `CustomLeaseExtension`.</span></span> <span data-ttu-id="8c0d4-141"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현은 `CustomLifetimeLease` 클래스에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-141">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> implementation is contained in `CustomLifetimeLease` class.</span></span> <span data-ttu-id="8c0d4-142"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드는 WCF 서비스 인스턴스를 해제 하려고 할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-142">The <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method is invoked when WCF is about to release the service instance.</span></span> <span data-ttu-id="8c0d4-143">그러나 ServiceBehavior의 `ISharedSessionInstance` 컬렉션에는 특정 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 구현의 인스턴스가 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-143">However, there is only one instance of a particular `ISharedSessionInstance` implementation in the ServiceBehavior’s <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> collection.</span></span> <span data-ttu-id="8c0d4-144">이 의미를 알 수 없는 <xref:System.ServiceModel.InstanceContext> WCF 확인 시 닫히는 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-144">This means there is no way of knowing the <xref:System.ServiceModel.InstanceContext> being closed at the time WCF checks the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span> <span data-ttu-id="8c0d4-145">따라서 이 샘플에서는 스레드 잠금을 사용하여 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> 메서드에 대한 요청을 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-145">Therefore this sample uses thread locking to serialize requests to the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.IsIdle%2A> method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c0d4-146">serialization은 응용 프로그램의 성능에 큰 영향을 주므로 스레드 잠금은 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-146">Using thread locking is not a recommended approach because serialization can severely affect the performance of your application.</span></span>  
  
 <span data-ttu-id="8c0d4-147">private 멤버 변수는 `CustomLeaseExtension` 클래스에서 `IsIdle` 값을 추적하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-147">A private member variable is used in the `CustomLeaseExtension` class to track the `IsIdle` value.</span></span> <span data-ttu-id="8c0d4-148"><xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> 값이 검색될 때마다 전용 멤버 `IsIdle`이 반환되고 `false`로 다시 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-148">Each time the value of <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider> is retrieved the `IsIdle` private member is returned and reset to `false`.</span></span> <span data-ttu-id="8c0d4-149">디스패처에서 `false` 메서드를 호출할 수 있도록 하려면 이 값을 <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A>로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-149">It is essential to set this value to `false` in order to make sure the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceContextProvider.NotifyIdle%2A> method.</span></span>  
  
```  
public bool IsIdle  
{  
    get   
    {  
       lock (thisLock)  
       {  
           bool idleCopy = isIdle;  
           isIdle = false;  
           return idleCopy;  
       }  
    }  
}  
```  
  
 <span data-ttu-id="8c0d4-150">`ISharedSessionLifetime.IsIdle` 속성이 `false`를 반환하는 경우 디스패처에서는 `NotifyIdle` 메서드를 사용하여 콜백 함수를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-150">If the `ISharedSessionLifetime.IsIdle` property returns `false` the Dispatcher registers a callback function by using the `NotifyIdle` method.</span></span> <span data-ttu-id="8c0d4-151">이 메서드는 해제되는 <xref:System.ServiceModel.InstanceContext>에 대한 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-151">This method receives a reference to the <xref:System.ServiceModel.InstanceContext> being released.</span></span> <span data-ttu-id="8c0d4-152">따라서 샘플 코드에서는 `ICustomLease` 형식 확장을 쿼리하고 확장 상태의 `ICustomLease.IsIdle` 속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-152">Therefore the sample code can query the `ICustomLease` type extension and check the `ICustomLease.IsIdle` property in the extended state.</span></span>  
  
```  
public void NotifyIdle(InstanceContextIdleCallback callback,   
            InstanceContext instanceContext)  
{  
    lock (thisLock)  
    {  
       ICustomLease customLease =  
           instanceContext.Extensions.Find<ICustomLease>();  
       customLease.Callback = callback;   
       isIdle = customLease.IsIdle;  
       if (isIdle)  
       {  
             callback(instanceContext);  
       }  
    }   
}  
```  
  
 <span data-ttu-id="8c0d4-153">`ICustomLease.IsIdle` 속성을 확인하기 전에 Callback 속성이 설정되어야 하며, 이는 `CustomLeaseExtension`이 유휴 상태가 될 때 디스패처에 이를 알리기 위해서 반드시 필요한 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-153">Before the `ICustomLease.IsIdle` property is checked the Callback property needs to be set as this is essential for `CustomLeaseExtension` to notify the Dispatcher when it becomes idle.</span></span> <span data-ttu-id="8c0d4-154">`ICustomLease.IsIdle`이 `true`를 반환하는 경우에는 `isIdle`에서 전용 멤버 `CustomLifetimeLease`이 `true`로 설정되고 callback 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-154">If `ICustomLease.IsIdle` returns `true`, the `isIdle` private member is simply set in `CustomLifetimeLease` to `true` and calls the callback method.</span></span> <span data-ttu-id="8c0d4-155">코드에서 잠금을 유지하므로 다른 스레드에서는 이 전용 멤버의 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-155">Because the code holds a lock, other threads cannot change the value of this private member.</span></span> <span data-ttu-id="8c0d4-156">다음에 디스패처에서 `ISharedSessionLifetime.IsIdle`을 확인할 때 이 멤버는 `true`를 반환하며 디스패처에서 인스턴스를 해제하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-156">And the next time Dispatcher checks the `ISharedSessionLifetime.IsIdle`, it returns `true` and lets Dispatcher release the instance.</span></span>  
  
 <span data-ttu-id="8c0d4-157">사용자 지정 확장의 기반이 완성된 후에는 이를 서비스 모델에 후크해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-157">Now that the groundwork for the custom extension is completed, it has to be hooked up to the service model.</span></span> <span data-ttu-id="8c0d4-158">후크 하는 `CustomLeaseExtension` 구현에는 <xref:System.ServiceModel.InstanceContext>, WCF 제공는 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 의 부트스트래핑을 수행 하는 인터페이스 <xref:System.ServiceModel.InstanceContext>합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-158">To hook up the `CustomLeaseExtension` implementation to the <xref:System.ServiceModel.InstanceContext>, WCF provides the <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> interface to perform the bootstrapping of <xref:System.ServiceModel.InstanceContext>.</span></span> <span data-ttu-id="8c0d4-159">샘플에서 `CustomLeaseInitializer` 클래스는 이 인터페이스를 구현하고 유일한 메서드 초기화에서 `CustomLeaseExtension` 컬렉션에 <xref:System.ServiceModel.InstanceContext.Extensions%2A>의 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-159">In the sample, the `CustomLeaseInitializer` class implements this interface and adds an instance of `CustomLeaseExtension` to the <xref:System.ServiceModel.InstanceContext.Extensions%2A> collection from the only method initialization.</span></span> <span data-ttu-id="8c0d4-160">이 메서드는 <xref:System.ServiceModel.InstanceContext>를 초기화하는 동안 디스패처에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-160">This method is called by Dispatcher while initializing the <xref:System.ServiceModel.InstanceContext>.</span></span>  
  
```  
public void Initialize(InstanceContext instanceContext, Message message)  
{  
  IExtension<InstanceContext> customLeaseExtension =  
    new CustomLeaseExtension(timeout);  
  instanceContext.Extensions.Add(customLeaseExtension);  
}  
```  
  
 <span data-ttu-id="8c0d4-161">마지막으로 `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` 및 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 는 구현이 모두 사용 하 여 서비스 모델까지 후크된는 <xref:System.ServiceModel.Description.IServiceBehavior> 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-161">Finally the `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` and <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> implementations are is hooked up to the service model by using the <xref:System.ServiceModel.Description.IServiceBehavior> implementation.</span></span> <span data-ttu-id="8c0d4-162">이 구현은 `CustomLeaseTimeAttribute` 클래스에 배치되며 `Attribute` 기본 클래스에서도 파생되어 이 동작을 특성으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-162">This implementation is placed in the `CustomLeaseTimeAttribute` class and it also derives from the `Attribute` base class to expose this behavior as an attribute.</span></span> <span data-ttu-id="8c0d4-163">`IServiceBehavior.ApplyBehavior` 메서드에서 <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> 및 `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` 구현의 인스턴스는 각각 `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes`의 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> 및 <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-163">In the `IServiceBehavior.ApplyBehavior` method, instances of <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer> and `System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime` implementations are added to the `System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextLifetimes` and <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceContextInitializers%2A> collections of the <xref:System.ServiceModel.Dispatcher.IShareableInstanceContextLifetime> respectively.</span></span>  
  
```  
public void ApplyBehavior(ServiceDescription description,   
           ServiceHostBase serviceHostBase,   
           Collection<DispatchBehavior> behaviors,  
           Collection<BindingParameterCollection> parameters)  
{  
    CustomLifetimeLease customLease = new CustomLifetimeLease();  
    CustomLeaseInitializer initializer =   
                new CustomLeaseInitializer(timeout);  
  
    foreach (DispatchBehavior dispatchBehavior in behaviors)  
    {  
        dispatchBehavior.InstanceContextLifetimes.Add(customLease);  
        dispatchBehavior.InstanceContextInitializers.Add(initializer);  
    }  
}  
```  
  
 <span data-ttu-id="8c0d4-164">`CustomLeaseTime` 특성으로 주석을 달아 이 동작을 샘플 서비스 클래스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-164">This behavior can be added to a sample service class by annotating it with the `CustomLeaseTime` attribute.</span></span>  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Shareable)]  
[CustomLeaseTime(Timeout = 20000)]  
public class EchoService : IEchoService  
{  
  //…  
}  
```  
  
 <span data-ttu-id="8c0d4-165">샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-165">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="8c0d4-166">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-166">Press ENTER in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8c0d4-167">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="8c0d4-167">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8c0d4-168">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-168">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8c0d4-169">C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-169">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8c0d4-170">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-170">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c0d4-171">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-171">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8c0d4-172">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-172">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8c0d4-173">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-173">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8c0d4-174">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c0d4-174">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Lifetime`  
  
## <a name="see-also"></a><span data-ttu-id="8c0d4-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c0d4-175">See Also</span></span>
