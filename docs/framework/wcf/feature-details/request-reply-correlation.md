---
title: 요청-회신 상관 관계
ms.date: 03/30/2017
ms.assetid: cf4379bf-2d08-43f3-9584-dfa30ffcb1f6
ms.openlocfilehash: c38854ad42ad4dddce5171482f3ddcfe5bd16b61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497206"
---
# <a name="request-reply-correlation"></a><span data-ttu-id="ed68b-102">요청-회신 상관 관계</span><span class="sxs-lookup"><span data-stu-id="ed68b-102">Request-Reply Correlation</span></span>
<span data-ttu-id="ed68b-103">요청-회신 상관 관계와 함께 사용 되는 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 쌍 및 워크플로 서비스에서 양방향 작업을 구현 하는 <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> 다른 웹에서 양방향 작업을 호출 하는 쌍 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-103">Request-reply correlation is used with a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair to implement a two-way operation in a workflow service and with a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair that invokes a two-way operation in another Web service.</span></span> <span data-ttu-id="ed68b-104">WCF 서비스에서 양방향 작업을 호출할 때 서비스는 기존의 될 수 있습니다 명령적 코드 기반 Windows Communication Foundation (WCF) 서비스 이거나 워크플로 서비스 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-104">When invoking a two-way operation in a WCF service, the service can be either a traditional imperative code-based Windows Communication Foundation (WCF) service or it can be a workflow service.</span></span> <span data-ttu-id="ed68b-105">요청-회신 상관 관계를 사용하려면 <xref:System.ServiceModel.BasicHttpBinding>과 같은 양방향 바인딩을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-105">To use request-reply correlation a two-way binding must be used, such as <xref:System.ServiceModel.BasicHttpBinding>.</span></span> <span data-ttu-id="ed68b-106">상관 관계 초기화 단계는 양방향 작업을 호출하는지 또는 양방향 작업을 구현하는지에 관계없이 비슷합니다. 이 단원에서는 이러한 상관 관계 초기화 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-106">Whether invoking or implementing a two-way operation, the correlation initialization steps are similar and are covered in this section.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-receivesendreply"></a><span data-ttu-id="ed68b-107">Receive/SendReply가 있는 양방향 작업에서 상관 관계 사용</span><span class="sxs-lookup"><span data-stu-id="ed68b-107">Using Correlation in a Two-Way Operation with Receive/SendReply</span></span>  
 <span data-ttu-id="ed68b-108">A <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 쌍은 워크플로 서비스에서 양방향 작업을 구현 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-108">A <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used to implement a two-way operation in a workflow service.</span></span> <span data-ttu-id="ed68b-109">런타임에서는 요청-회신 상관 관계를 사용하여 회신이 올바른 호출자에 디스패치되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-109">The runtime uses request-reply correlation to ensure that the reply is dispatched to the correct caller.</span></span> <span data-ttu-id="ed68b-110">워크플로가 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 사용하여 호스트되는 경우, 즉 서비스가 워크플로 서비스인 경우 기본 상관 관계 초기화로 충분합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-110">When a workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, which is the case for workflow services, then the default correlation initialization is sufficient.</span></span> <span data-ttu-id="ed68b-111">이 시나리오에서는 한 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 쌍을 사용 하 여 워크플로 통해 및 특정 상관 관계 구성은 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-111">In this scenario, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is used by a workflow, and no specific correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
### <a name="explicitly-initializing-request-reply-correlation"></a><span data-ttu-id="ed68b-112">명시적으로 요청-회신 상관 관계 초기화</span><span class="sxs-lookup"><span data-stu-id="ed68b-112">Explicitly Initializing Request-Reply Correlation</span></span>  
 <span data-ttu-id="ed68b-113">여러 개의 양방향 작업이 나란히 있는 경우 상관 관계를 명시적으로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-113">If other two-way operations are in parallel, then correlation should be explicitly configured.</span></span> <span data-ttu-id="ed68b-114">지정 하 여이 작업을 수행할 수 있습니다는 <xref:System.ServiceModel.Activities.CorrelationHandle> 및 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>를 배치 하 여는 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 내부에 <xref:System.ServiceModel.Activities.CorrelationScope>합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-114">This can be done by specifying a <xref:System.ServiceModel.Activities.CorrelationHandle> and <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>, or by placing the <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> inside of a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="ed68b-115">이 예제에서는 요청-회신 상관 관계에 구성 된 한 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 쌍입니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-115">In this example, request-reply correlation is configured on a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair.</span></span>  
  
```csharp  
Variable<CorrelationHandle> RRHandle = new Variable<CorrelationHandle>();  
  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder",  
    CorrelationInitializers =  
    {  
        new RequestReplyCorrelationInitializer  
        {  
            CorrelationHandle = RRHandle  
        }  
    }  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
// Construct a workflow using StartOrder and ReplyToStartOrder.  
```  
  
 <span data-ttu-id="ed68b-116">상관 관계를 명시적으로 구성하는 대신 <xref:System.ServiceModel.Activities.CorrelationScope> 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-116">Instead of explicitly configuring the correlation, a <xref:System.ServiceModel.Activities.CorrelationScope> activity can be used.</span></span> <span data-ttu-id="ed68b-117"><xref:System.ServiceModel.Activities.CorrelationScope>는 해당 작업에 포함된 메시징 작업에 암시적 <xref:System.ServiceModel.Activities.CorrelationHandle>을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-117"><xref:System.ServiceModel.Activities.CorrelationScope> provides an implicit <xref:System.ServiceModel.Activities.CorrelationHandle> to the messaging activities that it contains.</span></span> <span data-ttu-id="ed68b-118">이 예제에서는 <xref:System.ServiceModel.Activities.Receive> / <xref:System.ServiceModel.Activities.SendReply> 내 쌍이 포함 된 <xref:System.ServiceModel.Activities.CorrelationScope>합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-118">In this example, a <xref:System.ServiceModel.Activities.Receive>/<xref:System.ServiceModel.Activities.SendReply> pair is contained inside a <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span> <span data-ttu-id="ed68b-119">명시적 상관 관계 구성은 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-119">No explicit correlation configuration is required.</span></span>  
  
```csharp  
Receive StartOrder = new Receive  
{  
    CanCreateInstance = true,  
    ServiceContractName = OrderContractName,  
    OperationName = "StartOrder"  
};  
  
SendReply ReplyToStartOrder = new SendReply  
{  
    Request = StartOrder,  
    Content = … // Contains the return value, if any.  
};  
  
CorrelationScope s = new CorrelationScope  
{  
    Body = new Sequence  
    {  
        Activities =   
        {  
            StartOrder,  
            // Activities that create the reply.  
            ReplyToStartOrder  
        }  
    }  
};  
  
// Construct a workflow using the CorrelationScope.  
```  
  
 <span data-ttu-id="ed68b-120">추가 상관 관계가 필요한 경우 원하는 <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> 형식을 사용하여 해당 메시징 작업의 `CorrelationInitializer` 속성을 통해 필요한 상관 관계를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-120">If additional correlations are required then they can be configured using the <xref:System.ServiceModel.Activities.Send.CorrelationInitializers%2A> property of the respective messaging activities using the desired `CorrelationInitializer` types.</span></span>  
  
## <a name="using-correlation-in-a-two-way-operation-with-sendreceivereply"></a><span data-ttu-id="ed68b-121">Send/ReceiveReply가 있는 양방향 작업에서 상관 관계 사용</span><span class="sxs-lookup"><span data-stu-id="ed68b-121">Using Correlation in a Two-Way Operation with Send/ReceiveReply</span></span>  
 <span data-ttu-id="ed68b-122">반면는 <xref:System.ServiceModel.Activities.Receive> 작업에서 호스팅되는 워크플로 서비스에만 사용할 수 있습니다 <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> 및 <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> 쌍은 웹 서비스에서 메서드를 호출 해야 하는 모든 워크플로에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-122">While the <xref:System.ServiceModel.Activities.Receive> activity can only be used in a workflow service hosted by <xref:System.ServiceModel.Activities.WorkflowServiceHost>, <xref:System.ServiceModel.Activities.Send> and the <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair can be used in any workflow that must invoke a method on a Web service.</span></span> <span data-ttu-id="ed68b-123">워크플로가 <xref:System.ServiceModel.Activities.WorkflowServiceHost>를 사용하여 호스트된 경우 이전 단원에서 설명한 기본 상관 관계가 적용됩니다. 그렇지 않은 경우 원하는 <xref:System.ServiceModel.Activities.CorrelationInitializer> 및 <xref:System.ServiceModel.Activities.CorrelationHandle>을 명시적으로 사용하거나 <xref:System.ServiceModel.Activities.CorrelationScope>의 암시적 핸들 관리를 사용하여 상관 관계를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-123">If the workflow is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost> then the default correlation described in the previous section applies, but if not, then correlation must be configured either explicitly using the desired <xref:System.ServiceModel.Activities.CorrelationInitializer> and <xref:System.ServiceModel.Activities.CorrelationHandle>, or by using the implicit handle management of the <xref:System.ServiceModel.Activities.CorrelationScope>.</span></span>  
  
 <span data-ttu-id="ed68b-124">사용 하는 경우 **서비스 참조 추가** 양방향 작업이 있는 서비스의 경우 작업이 생성 됩니다를 래핑하는 <xref:System.ServiceModel.Activities.Send> / <xref:System.ServiceModel.Activities.ReceiveReply> 쌍 요청/회신 상관 관계를 내부적으로 작업을 명시적으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed68b-124">When using **Add Service Reference** on a service with two-way operations, activities are generated that wrap a <xref:System.ServiceModel.Activities.Send>/<xref:System.ServiceModel.Activities.ReceiveReply> pair activity internally with the Request/Reply correlation explicitly specified.</span></span>
