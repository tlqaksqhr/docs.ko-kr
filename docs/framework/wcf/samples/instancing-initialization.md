---
title: 인스턴싱 초기화
ms.date: 03/30/2017
ms.assetid: 154d049f-2140-4696-b494-c7e53f6775ef
ms.openlocfilehash: ae01254760219f2b408ef9d9663c4158e2802be8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807924"
---
# <a name="instancing-initialization"></a><span data-ttu-id="ac140-102">인스턴싱 초기화</span><span class="sxs-lookup"><span data-stu-id="ac140-102">Instancing Initialization</span></span>
<span data-ttu-id="ac140-103">이 샘플은 확장는 [풀링](../../../../docs/framework/wcf/samples/pooling.md) 인터페이스를 정의 하 여 샘플 `IObjectControl`, 활성화 및 비활성화 하 여 개체의 초기화를 사용자 지정입니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-103">This sample extends the [Pooling](../../../../docs/framework/wcf/samples/pooling.md) sample by defining an interface, `IObjectControl`, which customizes the initialization of an object by activating and deactivating it.</span></span> <span data-ttu-id="ac140-104">클라이언트에서는 개체를 풀로 반환하는 메서드와 개체를 풀로 반환하지 않는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-104">The client invokes methods that return the object to the pool and that do not return the object to the pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac140-105">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="extensibility-points"></a><span data-ttu-id="ac140-106">확장 지점</span><span class="sxs-lookup"><span data-stu-id="ac140-106">Extensibility Points</span></span>  
 <span data-ttu-id="ac140-107">Windows Communication Foundation (WCF) 확장을 만드는 첫 번째 단계 사용할 확장명 지점을 결정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-107">The first step in creating a Windows Communication Foundation (WCF) extension is to decide the extensibility point to use.</span></span> <span data-ttu-id="ac140-108">Wcf에서는 용어 *EndpointDispatcher* 들어오는 메시지를 사용자의 서비스에 대 한 메서드 호출으로 변환 하 고 보내는 메시지를 그 메서드의 반환 값 변환에 대 한 런타임 구성 요소 참조 .</span><span class="sxs-lookup"><span data-stu-id="ac140-108">In WCF, the term *EndpointDispatcher* refers to a run-time component responsible for converting incoming messages into method invocations on the user’s service and for converting return values from that method to an outgoing message.</span></span> <span data-ttu-id="ac140-109">WCF 서비스는 각 끝점에 대해 EndpointDispatcher를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-109">A WCF service creates an EndpointDispatcher for each endpoint.</span></span>  
  
 <span data-ttu-id="ac140-110">EndpointDispatcher는 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> 클래스를 사용하여 서비스에서 보내거나 받는 모든 메시지에 대해 끝점 범위 확장성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-110">The EndpointDispatcher offers endpoint scope (for all messages received or sent by the service) extensibility using the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> class.</span></span> <span data-ttu-id="ac140-111">이 클래스를 사용하면 EndpointDispatcher의 동작을 제어하는 다양한 속성을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-111">This class allows you to customize various properties that control the behavior of the EndpointDispatcher.</span></span> <span data-ttu-id="ac140-112">이 샘플에서는 서비스 클래스의 인스턴스를 제공하는 개체를 가리키는 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> 속성을 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-112">This sample focuses on the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property that points to the object that provides the instances of the service class.</span></span>  
  
## <a name="iinstanceprovider"></a><span data-ttu-id="ac140-113">IInstanceProvider</span><span class="sxs-lookup"><span data-stu-id="ac140-113">IInstanceProvider</span></span>  
 <span data-ttu-id="ac140-114">Wcf에서는 EndpointDispatcher를 구현 하는 인스턴스 공급자를 사용 하 여 서비스 클래스의 인스턴스를 만드는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-114">In WCF, the EndpointDispatcher creates instances of a service class by using an instance provider that implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface.</span></span> <span data-ttu-id="ac140-115">이 인터페이스에는 다음과 같은 두 개의 메서드만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-115">This interface has only two methods:</span></span>  
  
-   <span data-ttu-id="ac140-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: 메시지가 도착하면 디스패처가 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> 메서드를 호출하여 메시지를 처리할 서비스 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-116"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>: When a message arrives, the Dispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method to create an instance of the service class to process the message.</span></span> <span data-ttu-id="ac140-117">이 메서드의 호출 빈도는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-117">The frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span> <span data-ttu-id="ac140-118">예를 들어 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성이 <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>로 설정된 경우 도착하는 각 메시지를 처리하기 위해 서비스 클래스의 새 인스턴스가 만들어지므로, 메시지가 도착할 때마다 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-118">For example if the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property is set to <xref:System.ServiceModel.InstanceContextMode.PerCall?displayProperty=nameWithType>, a new instance of service class is created to process each message that arrives, so <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> is called whenever a message arrives.</span></span>  
  
-   <span data-ttu-id="ac140-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: 서비스 인스턴스가 메시지 처리 작업을 마치면 EndpointDispatcher는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-119"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A>: When the service instance finishes processing the message, the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.ReleaseInstance%2A> method.</span></span> <span data-ttu-id="ac140-120"><xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> 메서드에서와 마찬가지로 이 메서드의 호출 빈도는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-120">As in the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, the frequency of the calls to this method is determined by the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> property.</span></span>  
  
## <a name="the-object-pool"></a><span data-ttu-id="ac140-121">개체 풀</span><span class="sxs-lookup"><span data-stu-id="ac140-121">The Object Pool</span></span>  
 <span data-ttu-id="ac140-122">`ObjectPoolInstanceProvider` 클래스에는 개체 풀이 구현되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-122">The `ObjectPoolInstanceProvider` class contains the implementation for the object pool.</span></span> <span data-ttu-id="ac140-123">이 클래스는 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> 인터페이스를 구현하여 서비스 모델 계층과 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-123">This class implements the <xref:System.ServiceModel.Dispatcher.IInstanceProvider> interface to interact with the service model layer.</span></span> <span data-ttu-id="ac140-124">EndpointDispatcher가 새 인스턴스를 만드는 대신 <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> 메서드를 호출하면 사용자 지정 구현에서 메모리 내의 풀에 있는 기존 개체를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-124">When the EndpointDispatcher calls the <xref:System.ServiceModel.Dispatcher.IInstanceProvider.GetInstance%2A> method, instead of creating a new instance, the custom implementation looks for an existing object in an in-memory pool.</span></span> <span data-ttu-id="ac140-125">사용할 수 있는 개체가 있으면 반환되고,</span><span class="sxs-lookup"><span data-stu-id="ac140-125">If one is available, it is returned.</span></span> <span data-ttu-id="ac140-126">그렇지 않으면 `ObjectPoolInstanceProvider`는 `ActiveObjectsCount` 속성(풀에서 반환된 개체의 개수)이 최대 풀 크기에 도달했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-126">Otherwise, `ObjectPoolInstanceProvider` checks whether the `ActiveObjectsCount` property (number of objects returned from the pool) has reached the maximum pool size.</span></span> <span data-ttu-id="ac140-127">이 크기에 도달하지 않았으면 새 인스턴스가 만들어지고 호출자에게 반환하며 이어서 `ActiveObjectsCount`가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-127">If not, a new instance is created and returned to the caller and `ActiveObjectsCount` is subsequently incremented.</span></span> <span data-ttu-id="ac140-128">도달했으면 구성된 시간 동안 개체 만들기 요청이 큐에 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-128">Otherwise an object creation request is queued for a configured period of time.</span></span> <span data-ttu-id="ac140-129">`GetObjectFromThePool`의 구현은 다음 샘플 코드에 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-129">The implementation for `GetObjectFromThePool` is shown in the following sample code.</span></span>  
  
```  
private object GetObjectFromThePool()  
{  
    bool didNotTimeout =   
       availableCount.WaitOne(creationTimeout, true);  
    if(didNotTimeout)  
    {  
         object obj = null;  
         lock (poolLock)  
        {  
             if (pool.Count != 0)  
             {  
                   obj = pool.Pop();  
                   activeObjectsCount++;  
             }  
             else if (pool.Count == 0)  
             {  
                   if (activeObjectsCount < maxPoolSize)  
                   {  
                        obj = CreateNewPoolObject();  
                        activeObjectsCount++;  
  
                        #if (DEBUG)  
                        WritePoolMessage(  
                             ResourceHelper.GetString("MsgNewObject"));  
                       #endif  
                   }                          
            }  
           idleTimer.Stop();  
      }  
     // Call the Activate method if possible.  
    if (obj is IObjectControl)  
   {  
         ((IObjectControl)obj).Activate();  
   }  
   return obj;  
}  
throw new TimeoutException(  
ResourceHelper.GetString("ExObjectCreationTimeout"));  
}  
```  
  
 <span data-ttu-id="ac140-130">사용자 지정 `ReleaseInstance` 구현에서는 해제된 인스턴스를 다시 풀에 추가하고 `ActiveObjectsCount` 값을 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-130">The custom `ReleaseInstance` implementation adds the released instance back to the pool and decrements the `ActiveObjectsCount` value.</span></span> <span data-ttu-id="ac140-131">EndpointDispatcher는 서로 다른 스레드에서 이러한 메서드를 호출할 수 있기 때문에 `ObjectPoolInstanceProvider` 클래스의 클래스 수준 멤버에 대한 액세스를 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-131">The EndpointDispatcher can call these methods from different threads, and therefore synchronized access to the class level members in the `ObjectPoolInstanceProvider` class is required.</span></span>  
  
```  
public void ReleaseInstance(InstanceContext instanceContext, object instance)  
{  
    lock (poolLock)  
    {  
        // Check whether the object can be pooled.   
        // Call the Deactivate method if possible.  
        if (instance is IObjectControl)  
        {  
            IObjectControl objectControl = (IObjectControl)instance;  
            objectControl.Deactivate();  
  
            if (objectControl.CanBePooled)  
            {  
                pool.Push(instance);  
  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectPooled"));  
                #endif                          
            }  
            else  
            {  
                #if(DEBUG)  
                WritePoolMessage(  
                    ResourceHelper.GetString("MsgObjectWasNotPooled"));  
                #endif  
            }  
        }  
        else  
        {  
            pool.Push(instance);  
  
            #if(DEBUG)  
            WritePoolMessage(  
                ResourceHelper.GetString("MsgObjectPooled"));  
            #endif   
        }  
  
        activeObjectsCount--;  
  
        if (activeObjectsCount == 0)  
        {  
            idleTimer.Start();                       
        }  
    }  
  
    availableCount.Release(1);  
}  
```  
  
 <span data-ttu-id="ac140-132">`ReleaseInstance` 메서드는 제공 된 *정리 초기화* 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-132">The `ReleaseInstance` method provides a *clean up initialization* feature.</span></span> <span data-ttu-id="ac140-133">일반적으로 풀은 풀의 수명 동안 최소한의 개체 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-133">Normally the pool maintains a minimum number of objects for the lifetime of the pool.</span></span> <span data-ttu-id="ac140-134">하지만 사용량이 지나치게 많은 경우에는 구성에 지정된 최대 한도를 사용하기 위해 풀에 추가 개체를 만들어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-134">However, there can be periods of excessive usage that require creating additional objects in the pool to reach the maximum limit specified in the configuration.</span></span> <span data-ttu-id="ac140-135">결국 풀의 사용이 줄어들면 여분의 해당 개체는 추가 오버헤드가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-135">Eventually when the pool becomes less active those surplus objects can become an extra overhead.</span></span> <span data-ttu-id="ac140-136">따라서 `activeObjectsCount`가 0에 도달하면 정리 주기를 트리거하고 수행하는 유휴 타이머가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-136">Therefore when the `activeObjectsCount` reaches zero an idle timer is started that triggers and performs a clean-up cycle.</span></span>  
  
```  
if (activeObjectsCount == 0)  
{  
    idleTimer.Start();   
}  
```  
  
 <span data-ttu-id="ac140-137">ServiceModel 계층 확장은 다음 동작을 사용하여 후크됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-137">ServiceModel layer extensions are hooked up using the following behaviors:</span></span>  
  
-   <span data-ttu-id="ac140-138">서비스 동작: 전체 서비스 런타임을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-138">Service Behaviors: These allow for the customization of the entire service runtime.</span></span>  
  
-   <span data-ttu-id="ac140-139">끝점 동작: EndpointDispatcher를 포함한 특정 서비스 끝점을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-139">Endpoint Behaviors: These allow for the customization of a particular service endpoint, including the EndpointDispatcher.</span></span>  
  
-   <span data-ttu-id="ac140-140">계약 동작: 클라이언트 또는 서비스에서 각각 <xref:System.ServiceModel.Dispatcher.ClientRuntime> 또는 <xref:System.ServiceModel.Dispatcher.DispatchRuntime> 클래스를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-140">Contract Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientRuntime> or <xref:System.ServiceModel.Dispatcher.DispatchRuntime> classes on the client or the service respectively.</span></span>  
  
-   <span data-ttu-id="ac140-141">작업 동작: 클라이언트 또는 서비스에서 각각 <xref:System.ServiceModel.Dispatcher.ClientOperation> 또는 <xref:System.ServiceModel.Dispatcher.DispatchOperation> 클래스를 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-141">Operation Behaviors: These allow for the customization of either <xref:System.ServiceModel.Dispatcher.ClientOperation> or <xref:System.ServiceModel.Dispatcher.DispatchOperation> classes on the client or the service respectively.</span></span>  
  
 <span data-ttu-id="ac140-142">개체 풀링 확장을 위해 끝점 동작 또는 서비스 동작을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-142">For the purpose of an object pooling extension, either an endpoint behavior or a service behavior can be created.</span></span> <span data-ttu-id="ac140-143">이 예제에서는 서비스의 모든 끝점에 개체 풀링 기능을 적용하는 서비스 동작을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-143">In this example, we use a service behavior, which applies object pooling ability to every endpoint of the service.</span></span> <span data-ttu-id="ac140-144">서비스 동작은 <xref:System.ServiceModel.Description.IServiceBehavior> 인터페이스를 구현하여 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-144">Service behaviors are created by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface.</span></span> <span data-ttu-id="ac140-145">ServiceModel에 사용자 지정 동작을 인식시키는 방법에는 다음 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-145">There are several ways to make the ServiceModel aware of the custom behaviors:</span></span>  
  
-   <span data-ttu-id="ac140-146">사용자 지정 특성 사용</span><span class="sxs-lookup"><span data-stu-id="ac140-146">Using a custom attribute.</span></span>  
  
-   <span data-ttu-id="ac140-147">사용자 지정 동작을 서비스 설명의 동작 컬렉션에 명령적으로 추가</span><span class="sxs-lookup"><span data-stu-id="ac140-147">Imperatively adding it to the service description’s behaviors collection.</span></span>  
  
-   <span data-ttu-id="ac140-148">구성 파일 확장</span><span class="sxs-lookup"><span data-stu-id="ac140-148">Extending the configuration file.</span></span>  
  
 <span data-ttu-id="ac140-149">이 샘플에서는 사용자 지정 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-149">This sample uses a custom attribute.</span></span> <span data-ttu-id="ac140-150"><xref:System.ServiceModel.ServiceHost>가 생성되면 이는 서비스의 형식 정의에 사용된 특성을 확인하고 사용 가능한 동작을 서비스 설명의 동작 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-150">When the <xref:System.ServiceModel.ServiceHost> is constructed, it examines the attributes used in the service’s type definition and adds the available behaviors to the service description’s behaviors collection.</span></span>  
  
 <span data-ttu-id="ac140-151"><xref:System.ServiceModel.Description.IServiceBehavior> 인터페이스에는 세 가지 방법: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A> `,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A> `,` 및 <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-151">The <xref:System.ServiceModel.Description.IServiceBehavior> interface has three methods: <xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A>`,` <xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A>`,` and <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>.</span></span> <span data-ttu-id="ac140-152">WCF에서 이러한 메서드를 호출 하는 경우는 <xref:System.ServiceModel.ServiceHost> 초기화 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-152">These methods are called by WCF when the <xref:System.ServiceModel.ServiceHost> is being initialized.</span></span> <span data-ttu-id="ac140-153"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType>가 먼저 호출되어 서비스에 일관성을 검사할 수 있게 해 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-153"><xref:System.ServiceModel.Description.IServiceBehavior.Validate%2A?displayProperty=nameWithType> is called first; it allows the service to be inspected for inconsistencies.</span></span> <span data-ttu-id="ac140-154"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType>이 다음으로 호출됩니다. 이 메서드는 고급 시나리오에서만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-154"><xref:System.ServiceModel.Description.IServiceBehavior.AddBindingParameters%2A?displayProperty=nameWithType> is called next; this method is only required in very advanced scenarios.</span></span> <span data-ttu-id="ac140-155"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>가 마지막으로 호출되며 런타임 구성을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-155"><xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType> is called last and is responsible for configuring the runtime.</span></span> <span data-ttu-id="ac140-156">다음 매개 변수가 <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-156">The following parameters are passed into <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A?displayProperty=nameWithType>:</span></span>  
  
-   <span data-ttu-id="ac140-157">`Description`: 이 매개 변수는 전체 서비스에 대한 서비스 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-157">`Description`: This parameter provides the service description for the entire service.</span></span> <span data-ttu-id="ac140-158">이 매개 변수를 사용하여 서비스의 끝점, 계약, 바인딩 및 그 외 서비스와 관련된 데이터에 대한 설명 데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-158">This can be used to inspect description data about the service’s endpoints, contracts, bindings, and other data associated with the service.</span></span>  
  
-   <span data-ttu-id="ac140-159">`ServiceHostBase`: 이 매개 변수는 현재 초기화하고 있는 <xref:System.ServiceModel.ServiceHostBase>를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-159">`ServiceHostBase`: This parameter provides the <xref:System.ServiceModel.ServiceHostBase> that is currently being initialized.</span></span>  
  
 <span data-ttu-id="ac140-160">사용자 지정 <xref:System.ServiceModel.Description.IServiceBehavior> 구현에서는 `ObjectPoolInstanceProvider`의 새 인스턴스가 인스턴스화되어 <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A>에 첨부된 각 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>의 <xref:System.ServiceModel.ServiceHostBase> 속성에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-160">In the custom <xref:System.ServiceModel.Description.IServiceBehavior> implementation, a new instance of `ObjectPoolInstanceProvider` is instantiated and assigned to the <xref:System.ServiceModel.Dispatcher.DispatchRuntime.InstanceProvider%2A> property in each <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> that is attached to the <xref:System.ServiceModel.ServiceHostBase>.</span></span>  
  
```  
public void ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
{  
    if (enabled)  
    {  
        // Create an instance of the ObjectPoolInstanceProvider.  
        instanceProvider = new ObjectPoolInstanceProvider(description.ServiceType,  
        maxPoolSize, minPoolSize, creationTimeout);  
  
        // Assign our instance provider to Dispatch behavior in each   
        // endpoint.  
        foreach (ChannelDispatcherBase cdb in serviceHostBase.ChannelDispatchers)  
        {  
             ChannelDispatcher cd = cdb as ChannelDispatcher;  
             if (cd != null)  
             {  
                 foreach (EndpointDispatcher ed in cd.Endpoints)  
                 {  
                        ed.DispatchRuntime.InstanceProvider = instanceProvider;  
                 }  
             }  
         }  
     }  
}   
```  
  
 <span data-ttu-id="ac140-161"><xref:System.ServiceModel.Description.IServiceBehavior> 구현 외에 `ObjectPoolingAttribute` 클래스에도 특성 인수를 사용하여 개체 풀을 사용자 지정하는 멤버가 몇 개 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-161">In addition to an <xref:System.ServiceModel.Description.IServiceBehavior> implementation the `ObjectPoolingAttribute` class has several members to customize the object pool using the attribute arguments.</span></span> <span data-ttu-id="ac140-162">이러한 멤버에는 .NET Enterprise Services에서 제공하는 개체 풀링 기능 집합과 일치하는 `MaxSize`, `MinSize`, `Enabled` 및 `CreationTimeout`이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-162">These members include `MaxSize`, `MinSize`, `Enabled` and `CreationTimeout`, to match the object pooling feature set provided by .NET Enterprise Services.</span></span>  
  
 <span data-ttu-id="ac140-163">개체 풀링 동작 이제 추가할 수는 WCF 서비스를 새로 만든 사용자 지정 서비스 구현을 주석으로 지정 하 여 `ObjectPooling` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-163">The object pooling behavior can now be added to a WCF service by annotating the service implementation with the newly created custom `ObjectPooling` attribute.</span></span>  
  
```  
[ObjectPooling(MaxSize=1024, MinSize=10, CreationTimeout=30000]      
public class PoolService : IPoolService  
{  
  // …  
}  
```  
  
## <a name="hooking-activation-and-deactivation"></a><span data-ttu-id="ac140-164">활성화 및 비활성화 후크</span><span class="sxs-lookup"><span data-stu-id="ac140-164">Hooking Activation and Deactivation</span></span>  
 <span data-ttu-id="ac140-165">개체 풀링의 주요 목적은 만들고 초기화하는 데 비교적 자원이 많이 사용되는 수명이 짧은 개체를 최적화하는 데 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-165">The primary objective of object pooling is to optimize short-lived objects with relatively expensive creation and initialization.</span></span> <span data-ttu-id="ac140-166">따라서 개체 풀링을 제대로 사용하면 응용 프로그램의 성능을 현저히 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-166">Therefore it can give a dramatic performance boost to an application if properly used.</span></span> <span data-ttu-id="ac140-167">풀에서 개체가 반환되기 때문에 생성자는 한 번만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-167">Because the object is returned from the pool, the constructor is called only once.</span></span> <span data-ttu-id="ac140-168">반면 일부 응용 프로그램의 경우는 단일 컨텍스트 동안 사용된 리소스를 초기화하고 정리할 수 있도록 일정 수준의 제어가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-168">However, some applications require some level of control so that they can initialize and clean-up the resources used during a single context.</span></span> <span data-ttu-id="ac140-169">예를 들어 일련의 계산에 사용되는 개체는 다음 계산을 처리하기 전에 private 필드를 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-169">For example, an object being used for a set of calculations can reset its private fields before processing the next calculation.</span></span> <span data-ttu-id="ac140-170">엔터프라이즈 서비스에서는 개체 개발자가 `Activate` 기본 클래스의 `Deactivate` 및 <xref:System.EnterpriseServices.ServicedComponent> 메서드를 재정의할 수 있도록 하여 이러한 종류의 컨텍스트별 초기화를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-170">Enterprise Services enabled this kind of context-specific initialization by letting the object developer override `Activate` and `Deactivate` methods from the <xref:System.EnterpriseServices.ServicedComponent> base class.</span></span>  
  
 <span data-ttu-id="ac140-171">개체 풀은 풀에서 개체를 반환하기 바로 전에 `Activate` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-171">The object pool calls the `Activate` method just before returning the object from the pool.</span></span> <span data-ttu-id="ac140-172">개체가 풀로 다시 돌아갈 때 `Deactivate`가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-172">`Deactivate` is called when the object returns back to the pool.</span></span> <span data-ttu-id="ac140-173"><xref:System.EnterpriseServices.ServicedComponent> 기본 클래스에는 또한 개체를 계속 풀링할 수 있는지 여부를 풀에 알리는 데 사용되는 `boolean`라는 `CanBePooled` 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-173">The <xref:System.EnterpriseServices.ServicedComponent> base class also has a `boolean` property called `CanBePooled`, which can be used to notify the pool whether the object can be pooled further.</span></span>  
  
 <span data-ttu-id="ac140-174">이 기능을 모방하기 위해 이 샘플에서는 이전에 언급된 멤버가 있는 공용 인터페이스(`IObjectControl`)를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-174">To mimic this functionality, the sample declares a public interface (`IObjectControl`) that has the aforementioned members.</span></span> <span data-ttu-id="ac140-175">그런 다음 이 인터페이스는 컨텍스트별 초기화를 제공하는 데 사용되는 서비스 클래스에 의해 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-175">This interface is then implemented by service classes intended to provide context specific initialization.</span></span> <span data-ttu-id="ac140-176">이러한 요구 사항에 맞게 <xref:System.ServiceModel.Dispatcher.IInstanceProvider> 구현을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-176">The <xref:System.ServiceModel.Dispatcher.IInstanceProvider> implementation must be modified to meet these requirements.</span></span> <span data-ttu-id="ac140-177">이제 가져올 때마다 개체를 호출 하 여는 `GetInstance` 메서드를 확인 해야는 개체가 구현 하는지 `IObjectControl.` 를 호출 해야 합니다는 `Activate` 메서드 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-177">Now, each time you get an object by calling the `GetInstance` method, you must check whether the object implements `IObjectControl.` If it does, you must call the `Activate` method appropriately.</span></span>  
  
```  
if (obj is IObjectControl)  
{  
    ((IObjectControl)obj).Activate();  
}  
```  
  
 <span data-ttu-id="ac140-178">개체를 풀에 반환할 때는 개체를 다시 풀에 추가하기 전에 `CanBePooled` 속성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-178">When returning an object to the pool, a check is required for the `CanBePooled` property before adding the object back to the pool.</span></span>  
  
```  
if (instance is IObjectControl)  
{  
    IObjectControl objectControl = (IObjectControl)instance;  
    objectControl.Deactivate();  
    if (objectControl.CanBePooled)  
    {  
       pool.Push(instance);  
    }  
}  
```  
  
 <span data-ttu-id="ac140-179">서비스 개발자는 개체를 풀링할 수 있는지 여부를 결정할 수 있으므로 지정된 시간에 풀에 있는 개체 수가 최소 크기 아래로 내려갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-179">Because the service developer can decide whether an object can be pooled, the object count in the pool at a given time can go below the minimum size.</span></span> <span data-ttu-id="ac140-180">따라서 개체 수가 최소 수준 아래로 내려갔는지 확인하고 정리 절차에서 필요한 시작 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-180">Therefore you must check whether the object count has gone below the minimum level and perform the necessary initialization in the clean-up procedure.</span></span>  
  
```  
// Remove the surplus objects.  
if (pool.Count > minPoolSize)  
{  
  // Clean the surplus objects.  
}                      
else if (pool.Count < minPoolSize)  
{  
  // Reinitialize the missing objects.  
  while(pool.Count != minPoolSize)  
  {  
    pool.Push(CreateNewPoolObject());  
  }  
}  
```  
  
 <span data-ttu-id="ac140-181">샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-181">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="ac140-182">서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-182">Press Enter in each console window to shut down the service and client.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ac140-183">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="ac140-183">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="ac140-184">수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-184">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="ac140-185">지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-185">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="ac140-186">지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-186">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ac140-187">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-187">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ac140-188">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ac140-188">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ac140-189">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="ac140-189">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ac140-190">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac140-190">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Instancing\Initialization`  
  
## <a name="see-also"></a><span data-ttu-id="ac140-191">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac140-191">See Also</span></span>
