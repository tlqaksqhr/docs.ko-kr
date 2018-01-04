---
title: "순서에 상관없이 메시지 처리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33fc62a5-5d59-461c-a37a-0e1b51ac763d
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 19ab5afbc1eb13a3126e94a040d51204fea131a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="out-of-order-message-processing"></a><span data-ttu-id="85fe9-102">순서에 상관없이 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="85fe9-102">Out-of-Order Message Processing</span></span>
<span data-ttu-id="85fe9-103">워크플로 서비스는 특정 순서로 보내지는 메시지에 따라 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-103">Workflow services may depend on messages being sent in a specific order.</span></span> <span data-ttu-id="85fe9-104">워크플로 서비스는 하나 이상의 <xref:System.ServiceModel.Activities.Receive> 활동을 포함하고 각 <xref:System.ServiceModel.Activities.Receive> 활동은 특정 메시지를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-104">A workflow service contains one or more <xref:System.ServiceModel.Activities.Receive> activities and each <xref:System.ServiceModel.Activities.Receive> activity is expecting a specific message.</span></span> <span data-ttu-id="85fe9-105">특정 전송 전달 보장이 없으면 클라이언트가 보낸 메시지가 지연되어 워크플로 서비스가 예상할 수 없는 순서로 배달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-105">Without particular transport delivery guarantees, messages sent by clients may be delayed and therefore delivered in an order the workflow service may not expect.</span></span> <span data-ttu-id="85fe9-106">메시지를 순서에 상관없이 보내도 되는 워크플로 서비스를 구현하는 작업은 일반적으로 병렬 활동을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-106">Implementing a workflow service that does not require messages be sent in a specific order is normally done using a Parallel activity.</span></span> <span data-ttu-id="85fe9-107">복잡한 응용 프로그램 프로토콜의 경우 워크플로가 매우 빠른 속도로 매우 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-107">For a more complicated application protocol, the workflow would become very complex very quickly.</span></span>  <span data-ttu-id="85fe9-108">메시지를 순서에 상관없이 처리하는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 기능을 사용하면 중첩된 병렬 활동의 복잡도를 모두 제외한 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-108">The out-of-order message processing feature in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] allows you to create such a workflow without all of the complexity of nested Parallel activities.</span></span> <span data-ttu-id="85fe9-109">메시지를 순서에 상관없이 처리하는 기능은 <xref:System.ServiceModel.Channels.ReceiveContext> MSMQ 바인딩 같은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 지원하는 채널에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-109">Out-of-order message processing is only supported on channels that support <xref:System.ServiceModel.Channels.ReceiveContext> such as the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] MSMQ bindings.</span></span>  
  
## <a name="enabling-out-of-order-message-processing"></a><span data-ttu-id="85fe9-110">메시지를 순서에 상관없이 처리하는 기능 사용</span><span class="sxs-lookup"><span data-stu-id="85fe9-110">Enabling Out-Of-Order Message Processing</span></span>  
 <span data-ttu-id="85fe9-111">메시지를 순서에 상관없이 처리하는 기능을 사용하려면 WorkflowService의 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-111">Out-of-order message processing is enabled by setting the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property to `true` on the WorkflowService.</span></span> <span data-ttu-id="85fe9-112">다음 예제에서는 코드에서 <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> 속성을 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-112">The following example shows how to set the <xref:System.ServiceModel.Activities.WorkflowService.AllowBufferedReceive%2A> property in code.</span></span>  
  
```csharp  
// Code: Opt-in to Buffered Receive processing...  
WorkflowService service = new WorkflowService  
{  
    Name="MyService",  
    Body = workflow,  
    AllowBufferedReceive = true  
};  
```  
  
 <span data-ttu-id="85fe9-113">또한 다음 예제와 같이 XAML에서 워크플로 서비스에 `AllowBufferedReceive` 특성을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fe9-113">You can also apply the `AllowBufferedReceive` attribute to a workflow service in XAML as shown in the following example.</span></span>  
  
```xaml  
// Xaml: Opt-in to Buffered Receive processing...  
<WorkflowService AllowBufferedReceive="True">  
   <!—the actual children activities -->  
</Sequence>  
```  
  
## <a name="see-also"></a><span data-ttu-id="85fe9-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85fe9-114">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ReceiveContext>  
 [<span data-ttu-id="85fe9-115">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="85fe9-115">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="85fe9-116">큐 및 신뢰할 수 있는 세션</span><span class="sxs-lookup"><span data-stu-id="85fe9-116">Queues and Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)
