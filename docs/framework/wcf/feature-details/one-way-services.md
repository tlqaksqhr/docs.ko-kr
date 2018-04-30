---
title: 단방향 서비스
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], one-way service contracts
- WCF [WCF], one-way service contracts
- service contracts [WCF], defining one-way
ms.assetid: 19053a36-4492-45a3-bfe6-0365ee0205a3
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 380f6a10994c7eb69f4a59b222aa2d422151f247
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="one-way-services"></a><span data-ttu-id="c4446-102">단방향 서비스</span><span class="sxs-lookup"><span data-stu-id="c4446-102">One-Way Services</span></span>
<span data-ttu-id="c4446-103">서비스 작업의 기본 동작은 요청-회신 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-103">The default behavior of a service operation is the request-reply pattern.</span></span> <span data-ttu-id="c4446-104">요청-회신 패턴의 경우 서비스 작업이 `void` 메서드로 코드에 표현된 경우에도 클라이언트에서 회신 메시지를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-104">In a request-reply pattern, the client waits for the reply message, even if the service operation is represented in code as a `void` method.</span></span> <span data-ttu-id="c4446-105">단방향 작업을 사용하는 경우 하나의 메시지만 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-105">With a one-way operation, only one message is transmitted.</span></span> <span data-ttu-id="c4446-106">수신자는 회신 메시지를 보내지 않으며 발신자도 메시지를 기다리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-106">The receiver does not send a reply message, nor does the sender expect one.</span></span>  
  
 <span data-ttu-id="c4446-107">다음과 같은 경우 단방향 디자인 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-107">Use the one-way design pattern:</span></span>  
  
-   <span data-ttu-id="c4446-108">클라이언트가 작업을 호출해야 하며 작업 수준에서 작업 결과에 영향을 받지 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="c4446-108">When the client must call operations and is not affected by the result of the operation at the operation level.</span></span>  
  
-   <span data-ttu-id="c4446-109"><xref:System.ServiceModel.NetMsmqBinding> 또는 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> 클래스를 사용하는 경우.</span><span class="sxs-lookup"><span data-stu-id="c4446-109">When using the <xref:System.ServiceModel.NetMsmqBinding> or the <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> class.</span></span> <span data-ttu-id="c4446-110">(이 시나리오에 대 한 자세한 내용은 참조 [WCF의 큐](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md).)</span><span class="sxs-lookup"><span data-stu-id="c4446-110">(For more information about this scenario, see [Queues in WCF](../../../../docs/framework/wcf/feature-details/queues-in-wcf.md).)</span></span>  
  
 <span data-ttu-id="c4446-111">단방향 작업의 경우 오류 정보를 클라이언트로 전달하는 응답 메시지가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-111">When an operation is one-way, there is no response message to carry error information back to the client.</span></span> <span data-ttu-id="c4446-112">신뢰할 수 있는 세션과 같은 기본 바인딩의 기능을 사용하거나 두 개의 단방향 작업(하나는 서비스 작업을 호출하기 위한 클라이언트에서 서비스로의 단방향 계약이며, 다른 하나는 서비스가 클라이언트에서 구현하는 콜백을 사용하여 오류를 다시 클라이언트에 전달할 수 있는 서비스와 클라이언트 간 단방향 계약)을 사용하는 이중 서비스 계약을 디자인하여 오류 상태를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-112">You can detect error conditions by using features of the underlying binding, such as reliable sessions, or by designing a duplex service contract that uses two one-way operations—a one-way contract from the client to the service to call service operation and another one-way contract between the service and the client so that the service can send back faults to the client using a callback that the client implements.</span></span>  
  
 <span data-ttu-id="c4446-113">단방향 서비스 계약을 만들려면 다음 샘플 코드에서처럼 서비스 계약을 정의하고, <xref:System.ServiceModel.OperationContractAttribute> 클래스를 각 작업에 적용하여, <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-113">To create a one-way service contract, define your service contract, apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, and set the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true`, as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOneWayCalculator  
{  
    [OperationContract(IsOneWay=true)]  
    void Add(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Subtract(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Multiply(double n1, double n2);  
    [OperationContract(IsOneWay = true)]  
    void Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="c4446-114">전체 예제에 대 한 참조는 [단방향](../../../../docs/framework/wcf/samples/one-way.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="c4446-114">For a complete example, see the [One-Way](../../../../docs/framework/wcf/samples/one-way.md) sample.</span></span>  
  
## <a name="clients-blocking-with-one-way-operations"></a><span data-ttu-id="c4446-115">단방향 작업을 사용하여 클라이언트 차단</span><span class="sxs-lookup"><span data-stu-id="c4446-115">Clients Blocking with One-Way Operations</span></span>  
 <span data-ttu-id="c4446-116">일부 단방향 응용 프로그램은 아웃바운드 데이터가 네트워크 연결에 쓰여지면 반환되는 반면 몇몇 시나리오의 경우 바인딩 또는 서비스를 구현하면 단방향 작업을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-116">It is important to realize that while some one-way applications return as soon as the outbound data is written to the network connection, in several scenarios the implementation of a binding or of a service can cause a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to block using one-way operations.</span></span> <span data-ttu-id="c4446-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 응용 프로그램의 경우 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 개체는 아웃바운드 데이터가 네트워크 연결에 쓰여지기 전에는 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-117">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client applications, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client object does not return until the outbound data has been written to the network connection.</span></span> <span data-ttu-id="c4446-118">이는 단방향 작업을 비롯한 모든 메시지 교환 패턴에 적용되며, 전송에 데이터를 쓰는 동안 발생한 문제로 인해 클라이언트가 반환될 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-118">This is true for all message exchange patterns, including one-way operations; this means that any problem writing the data to the transport prevents the client from returning.</span></span> <span data-ttu-id="c4446-119">문제에 따라 예외가 발생하거나 메시지를 서비스에 보낼 때 지연될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-119">Depending upon the problem, the result could be an exception or a delay in sending messages to the service.</span></span>  
  
 <span data-ttu-id="c4446-120">예를 들어, 전송에서 끝점을 찾을 수 없는 경우 장시간 지연되지 않고 <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-120">For example, if the transport cannot find the endpoint, a <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType> exception is thrown without much delay.</span></span> <span data-ttu-id="c4446-121">그러나 다른 이유로 연결이 끊어져 서비스에서 데이터를 읽지 못하게 될 수도 있어 클라이언트 전송의 보내기 작업이 반환될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-121">However, it is also possible that the service is unable to read the data off the wire for some reason, which prevents the client transport send operation from returning.</span></span> <span data-ttu-id="c4446-122">이 경우 클라이언트 전송 바인딩의 <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A?displayProperty=nameWithType> 기간을 초과하면 <xref:System.TimeoutException?displayProperty=nameWithType>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-122">In these cases, if the <xref:System.ServiceModel.Channels.Binding.SendTimeout%2A?displayProperty=nameWithType> period on the client transport binding is exceeded, a <xref:System.TimeoutException?displayProperty=nameWithType> is thrown—but not until the timeout period has been exceeded.</span></span> <span data-ttu-id="c4446-123">서비스에 너무 많은 메시지가 발생되어 서비스가 특정 지점 이후부터는 메시지를 처리할 수 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-123">It is also possible to fire so many messages at a service that the service cannot process them past a certain point.</span></span> <span data-ttu-id="c4446-124">이 경우에도 서비스가 메시지를 처리할 수 있게 되거나 예외가 throw될 때까지 단방향 클라이언트가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-124">In this case, too, the one-way client blocks until the service can process the messages or until an exception is thrown.</span></span>  
  
 <span data-ttu-id="c4446-125">이 이외에도 서비스의 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> 속성이 <xref:System.ServiceModel.ConcurrencyMode.Single>로 설정되고 바인딩에 세션을 사용하는 경우가 해당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-125">Another variation is the situation in which the service <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> property is set to <xref:System.ServiceModel.ConcurrencyMode.Single> and the binding uses sessions.</span></span> <span data-ttu-id="c4446-126">이 경우 디스패처는 세션의 요구 사항에 따라 들어오는 메시지에 순서를 지정하므로, 서비스에서 해당 세션의 이전 메시지를 처리할 때까지는 연결이 끊어져 다음 메시지를 읽을 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-126">In this case, the dispatcher enforces ordering on the incoming messages (a requirement of sessions), which prevents subsequent messages from being read off the network until the service has processed the preceding message for that session.</span></span> <span data-ttu-id="c4446-127">마찬가지로 클라이언트가 차단되지만, 예외 발생 여부는 클라이언트에 설정된 제한 시간 이전에 기다리는 데이터를 서비스가 처리할 수 있는지에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-127">Again, the client blocks, but whether an exception occurs depends upon whether the service is able to process the waiting data prior to the timeout settings on the client.</span></span>  
  
 <span data-ttu-id="c4446-128">이 문제는 클라이언트 개체와 클라이언트 전송의 보내기 작업 사이에 버퍼를 삽입하여 어느 정도 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-128">You can mitigate some of this problem by inserting a buffer between the client object and the client transport's send operation.</span></span> <span data-ttu-id="c4446-129">예를 들어, 비동기 호출을 사용하거나 메모리 내 메시지 큐를 사용하면 클라이언트 개체가 빠르게 반환되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-129">For example, using asynchronous calls or using an in-memory message queue can enable the client object to return quickly.</span></span> <span data-ttu-id="c4446-130">두 방법 모두 기능을 향상시키지만 스레드 풀과 메시지 큐의 크기가 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-130">Both approaches may increase functionality, but the size of the thread pool and the message queue still enforce limits.</span></span>  
  
 <span data-ttu-id="c4446-131">따라서 서비스와 클라이언트의 여러 가지 컨트롤을 검사한 다음 응용 프로그램 시나리오를 테스트하여 서비스 또는 클라이언트에 대한 최상의 구성을 결정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-131">It is recommended, instead, that you examine the various controls on the service as well as on the client, and then test your application scenarios to determine the best configuration on either side.</span></span> <span data-ttu-id="c4446-132">예를 들어, 세션 사용으로 인해 서비스에서 메시지 처리가 차단되는 경우 각 메시지가 다른 서비스 인스턴스에 의해 처리될 수 있도록 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> 속성을 <xref:System.ServiceModel.InstanceContextMode.PerCall>로 설정하고, 한 번에 둘 이상의 스레드에서 메시지를 디스패치할 수 있도록 <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>를 <xref:System.ServiceModel.ConcurrencyMode.Multiple>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-132">For example, if the use of sessions is blocking the processing of messages on your service, you can set the <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> property to <xref:System.ServiceModel.InstanceContextMode.PerCall> so that each message can be processed by a different service instance, and set the <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> to <xref:System.ServiceModel.ConcurrencyMode.Multiple> in order to allow more than one thread to dispatch messages at a time.</span></span> <span data-ttu-id="c4446-133">또 다른 방법은 서비스 및 클라이언트 바인딩의 읽기 할당량을 늘리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c4446-133">Another approach is to increase the read quotas of the service and client bindings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4446-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4446-134">See Also</span></span>  
 [<span data-ttu-id="c4446-135">단방향</span><span class="sxs-lookup"><span data-stu-id="c4446-135">One-Way</span></span>](../../../../docs/framework/wcf/samples/one-way.md)
