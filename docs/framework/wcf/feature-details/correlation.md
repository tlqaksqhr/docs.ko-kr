---
title: "상관 관계"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fc1608cc4e746af56e7d89237f0c1f5e6cc3bc7e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="correlation"></a><span data-ttu-id="fd7b6-102">상관 관계</span><span class="sxs-lookup"><span data-stu-id="fd7b6-102">Correlation</span></span>
<span data-ttu-id="fd7b6-103">워크플로 서비스 응용 프로그램이 다른 서비스와 통신할 때는 둘 사이의 메시지가 적절한 워크플로 인스턴스에 디스패치되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="fd7b6-104">상관 관계는 이를 위한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="fd7b6-105">이 단원의 항목에서는 상관 관계의 개요를 제공하고 다양한 워크플로 서비스 시나리오에서 상관 관계를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fd7b6-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="fd7b6-106">In This Section</span></span>  
 [<span data-ttu-id="fd7b6-107">상관 관계 개요</span><span class="sxs-lookup"><span data-stu-id="fd7b6-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="fd7b6-108">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서 사용할 수 있는 상관 관계의 형식에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="fd7b6-109">컨텍스트 교환</span><span class="sxs-lookup"><span data-stu-id="fd7b6-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="fd7b6-110">컨텍스트 교환 상관 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="fd7b6-111">영 속 이중</span><span class="sxs-lookup"><span data-stu-id="fd7b6-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="fd7b6-112">영속 이중 상관 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="fd7b6-113">내용 기반</span><span class="sxs-lookup"><span data-stu-id="fd7b6-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="fd7b6-114">내용 기반 상관 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="fd7b6-115">요청-회신</span><span class="sxs-lookup"><span data-stu-id="fd7b6-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="fd7b6-116">요청-회신 상관 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="fd7b6-117">상관 관계 문제 해결</span><span class="sxs-lookup"><span data-stu-id="fd7b6-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="fd7b6-118">상관 관계 문제를 해결하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fd7b6-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7b6-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd7b6-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="fd7b6-120">내용 기반 상관 관계</span><span class="sxs-lookup"><span data-stu-id="fd7b6-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="fd7b6-121">상호 관련 된 계산기</span><span class="sxs-lookup"><span data-stu-id="fd7b6-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
