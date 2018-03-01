---
title: "Windows Communication Foundation 끝점"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0725c4f4275853cce958072a57d7f6ca4059e8cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="d4ba4-102">Windows Communication Foundation 끝점</span><span class="sxs-lookup"><span data-stu-id="d4ba4-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="d4ba4-103">와 모든 통신은 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스를 통해 발생 된 *끝점* 서비스의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-103">All communication with a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="d4ba4-104">끝점은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스에서 제공하는 기능에 대한 클라이언트 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-104">Endpoints provide clients access to the functionality that a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service offers.</span></span>  
  
 <span data-ttu-id="d4ba4-105">끝점을 만드는 방법에 대 한 개요를 참조 하십시오. [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="d4ba4-106">각 끝점에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-106">Each endpoint contains:</span></span>  
  
-   <span data-ttu-id="d4ba4-107">끝점을 찾을 위치를 나타내는 주소</span><span class="sxs-lookup"><span data-stu-id="d4ba4-107">An address that indicates where to find the endpoint.</span></span>  
  
-   <span data-ttu-id="d4ba4-108">클라이언트가 끝점과 통신할 수 있는 방법을 지정하는 바인딩</span><span class="sxs-lookup"><span data-stu-id="d4ba4-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="d4ba4-109">사용 가능한 메서드를 식별하는 계약</span><span class="sxs-lookup"><span data-stu-id="d4ba4-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="d4ba4-110">끝점의 개별 부분을 지정하는 방법에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
-   [<span data-ttu-id="d4ba4-111">끝점 주소 지정</span><span class="sxs-lookup"><span data-stu-id="d4ba4-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [<span data-ttu-id="d4ba4-112">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d4ba4-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [<span data-ttu-id="d4ba4-113">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="d4ba4-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="d4ba4-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d4ba4-114">In This Section</span></span>  
 [<span data-ttu-id="d4ba4-115">끝점 만들기 개요</span><span class="sxs-lookup"><span data-stu-id="d4ba4-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="d4ba4-116">끝점의 구조에 대해 설명하고 구성 및 코드에서 끝점을 정의하는 방법을 간략하게 설명합니다. 또한 런타임에서 제공하는 기본 끝점, 바인딩 및 동작을 사용하는 방법에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="d4ba4-117">끝점 주소 지정</span><span class="sxs-lookup"><span data-stu-id="d4ba4-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="d4ba4-118">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와의 통신이 끝점을 통해 수행되는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-118">Describes how communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="d4ba4-119">방법: 구성에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="d4ba4-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="d4ba4-120">구성에서 서비스 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="d4ba4-121">방법: 코드에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="d4ba4-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="d4ba4-122">코드에서 서비스 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="d4ba4-123">메타데이터 끝점 게시</span><span class="sxs-lookup"><span data-stu-id="d4ba4-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="d4ba4-124">구성 및 코드에서 메타데이터 끝점을 게시하여 메타데이터를 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4ba4-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d4ba4-125">참조</span><span class="sxs-lookup"><span data-stu-id="d4ba4-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="d4ba4-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d4ba4-126">Related Sections</span></span>  
 [<span data-ttu-id="d4ba4-127">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="d4ba4-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
