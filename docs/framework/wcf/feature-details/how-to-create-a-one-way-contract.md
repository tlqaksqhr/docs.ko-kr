---
title: "방법: 단방향 계약 만들기"
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
ms.assetid: 85084cd9-31cc-4e95-b667-42ef01336622
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f93247a96501359bcda8d2956308e6570c597f93
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-one-way-contract"></a><span data-ttu-id="5f86b-102">방법: 단방향 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="5f86b-102">How to: Create a One-Way Contract</span></span>
<span data-ttu-id="5f86b-103">이 항목에서는 단방향 계약을 사용하는 메서드를 만드는 기본 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-103">This topic shows the basic steps to create methods that use a one-way contract.</span></span> <span data-ttu-id="5f86b-104">이러한 메서드는 클라이언트로부터 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에 대한 작업을 호출하지만 회신을 기다리지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-104">Such methods invoke operations on a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service from a client but do not expect a reply.</span></span> <span data-ttu-id="5f86b-105">이러한 형식의 계약은 예를 들어 여러 구독자에게 알림을 게시하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-105">This type of contract can be used, for example, to publish notifications to many subscribers.</span></span> <span data-ttu-id="5f86b-106">또한 이중(양방향) 계약을 만들 때 단방향 계약을 사용할 수 있으며 이를 통해 클라이언트 및 서버가 각각 독립적으로 통신하므로 서로 호출을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-106">You can also use one-way contracts when creating a duplex (two-way) contract, which allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="5f86b-107">특히 이 기능을 통해 서버는 클라이언트가 이벤트로 처리할 수 있는 클라이언트에 대한 단방향 호출을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-107">This can allow, in particular, the server to make one-way calls to the client that the client can treat as events.</span></span> <span data-ttu-id="5f86b-108">단방향 메서드 지정에 대한 자세한 내용은 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> 속성 및 <xref:System.ServiceModel.OperationContractAttribute> 클래스를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5f86b-108">For detailed information about specifying one-way methods, see the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property and the <xref:System.ServiceModel.OperationContractAttribute> class.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="5f86b-109">이중 계약에 대 한 클라이언트 응용 프로그램을 만드는 참조 [하는 방법: 단방향와 함께 Access Services 및 요청-회신 계약](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-109"> creating a client application for a duplex contract, see [How to: Access Services with One-Way and Request-Reply Contracts](../../../../docs/framework/wcf/feature-details/how-to-access-wcf-services-with-one-way-and-request-reply-contracts.md).</span></span> <span data-ttu-id="5f86b-110">작업 예제에 대 한 참조는 [단방향](../../../../docs/framework/wcf/samples/one-way.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="5f86b-110">For a working sample, see the [One-Way](../../../../docs/framework/wcf/samples/one-way.md) sample.</span></span>  
  
### <a name="to-create-a-one-way-contract"></a><span data-ttu-id="5f86b-111">단방향 계약을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5f86b-111">To create a one-way contract</span></span>  
  
1.  <span data-ttu-id="5f86b-112"><xref:System.ServiceModel.ServiceContractAttribute> 클래스를 서비스가 구현할 메서드를 정의하는 인터페이스에 적용하여 서비스 계약을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-112">Create the service contract by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface that defines the methods the service is to implement.</span></span>  
  
2.  <span data-ttu-id="5f86b-113"><xref:System.ServiceModel.OperationContractAttribute> 클래스를 클라이언트가 호출할 수 있는 인터페이스의 메서드에 적용하여 해당 메서드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-113">Indicate which methods in the interface a client can invoked by applying the <xref:System.ServiceModel.OperationContractAttribute> class to them.</span></span>  
  
3.  <span data-ttu-id="5f86b-114">출력이 없는 작업(반환 값이 없고 out 또는 ref 매개 변수가 없음)은 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> 속성을 `true`로 설정하여 단방향으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-114">Designate operations that must have no output (no return value and no out or ref parameters) as one-way by setting the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true`.</span></span> <span data-ttu-id="5f86b-115"><xref:System.ServiceModel.OperationContractAttribute> 클래스가 있는 작업은 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> 속성이 기본적으로 `false`이기 때문에 기본적으로 요청-회신 계약을 충족합니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-115">Note that the operations that carry the <xref:System.ServiceModel.OperationContractAttribute> class satisfy a request-reply contract by default because the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property is `false` by default.</span></span> <span data-ttu-id="5f86b-116">따라서 메서드에 대한 단방향 계약을 원하는 경우 특성 속성 값을 명시적으로 `true`로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-116">So you must explicitly specify the value of the attribute property to be `true` if you want a one-way contract for the method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f86b-117">예제</span><span class="sxs-lookup"><span data-stu-id="5f86b-117">Example</span></span>  
 <span data-ttu-id="5f86b-118">다음 코드 예제에서는 여러 단방향 메서드를 포함하는 서비스에 대한 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-118">The following code example defines a contract for a service that includes several one-way methods.</span></span> <span data-ttu-id="5f86b-119">기본값이 요청-회신이며 결과를 반환하는 `Equals`를 제외하고 모든 메서드에는 단방향 계약이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f86b-119">All of the methods have one-way contracts except `Equals`, which defaults to request-reply and returns a result.</span></span>  
  
 [!code-csharp[S_Service_Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_service_session/cs/service.cs#1)]
 [!code-vb[S_Service_Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_service_session/vb/service.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5f86b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5f86b-120">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="5f86b-121">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="5f86b-121">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [<span data-ttu-id="5f86b-122">방법: 서비스 계약 정의</span><span class="sxs-lookup"><span data-stu-id="5f86b-122">How to: Define a Service Contract</span></span>](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="5f86b-123">세션</span><span class="sxs-lookup"><span data-stu-id="5f86b-123">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)  
 [<span data-ttu-id="5f86b-124">방법: 이중 계약 만들기</span><span class="sxs-lookup"><span data-stu-id="5f86b-124">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
