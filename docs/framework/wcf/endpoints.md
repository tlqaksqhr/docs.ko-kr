---
title: Windows Communication Foundation 끝점
ms.date: 03/30/2017
helpviewer_keywords:
- endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
ms.openlocfilehash: b55abe937701f8708643efa2ea4cb62514b3521b
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="ce0ba-102">Windows Communication Foundation 끝점</span><span class="sxs-lookup"><span data-stu-id="ce0ba-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="ce0ba-103">Windows Communication Foundation (WCF) 서비스와 모든 통신을 통해 발생 된 *끝점* 서비스의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-103">All communication with a Windows Communication Foundation (WCF) service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="ce0ba-104">끝점 클라이언트는 WCF 서비스에서 제공 하는 기능에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-104">Endpoints provide clients access to the functionality that a WCF service offers.</span></span>  
  
 <span data-ttu-id="ce0ba-105">끝점을 만드는 방법에 대 한 개요를 참조 하십시오. [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="ce0ba-106">각 끝점에는 다음이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-106">Each endpoint contains:</span></span>  
  
-   <span data-ttu-id="ce0ba-107">끝점을 찾을 위치를 나타내는 주소</span><span class="sxs-lookup"><span data-stu-id="ce0ba-107">An address that indicates where to find the endpoint.</span></span>  
  
-   <span data-ttu-id="ce0ba-108">클라이언트가 끝점과 통신할 수 있는 방법을 지정하는 바인딩</span><span class="sxs-lookup"><span data-stu-id="ce0ba-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="ce0ba-109">사용 가능한 메서드를 식별하는 계약</span><span class="sxs-lookup"><span data-stu-id="ce0ba-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="ce0ba-110">끝점의 개별 부분을 지정하는 방법에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
-   [<span data-ttu-id="ce0ba-111">끝점 주소 지정</span><span class="sxs-lookup"><span data-stu-id="ce0ba-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [<span data-ttu-id="ce0ba-112">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="ce0ba-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [<span data-ttu-id="ce0ba-113">서비스 디자인 및 구현</span><span class="sxs-lookup"><span data-stu-id="ce0ba-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="ce0ba-114">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="ce0ba-114">In This Section</span></span>  
 [<span data-ttu-id="ce0ba-115">끝점 만들기 개요</span><span class="sxs-lookup"><span data-stu-id="ce0ba-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="ce0ba-116">끝점의 구조에 대해 설명하고 구성 및 코드에서 끝점을 정의하는 방법을 간략하게 설명합니다. 또한 런타임에서 제공하는 기본 끝점, 바인딩 및 동작을 사용하는 방법에 대해서도 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="ce0ba-117">끝점 주소 지정</span><span class="sxs-lookup"><span data-stu-id="ce0ba-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="ce0ba-118">끝점을 통해 WCF 서비스와의 통신을 수행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-118">Describes how communication with a WCF service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="ce0ba-119">방법: 구성에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="ce0ba-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="ce0ba-120">구성에서 서비스 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="ce0ba-121">방법: 코드에서 서비스 끝점 만들기</span><span class="sxs-lookup"><span data-stu-id="ce0ba-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="ce0ba-122">코드에서 서비스 끝점을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="ce0ba-123">메타데이터 끝점 게시</span><span class="sxs-lookup"><span data-stu-id="ce0ba-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="ce0ba-124">구성 및 코드에서 메타데이터 끝점을 게시하여 메타데이터를 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce0ba-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ce0ba-125">참조</span><span class="sxs-lookup"><span data-stu-id="ce0ba-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="ce0ba-126">관련 단원</span><span class="sxs-lookup"><span data-stu-id="ce0ba-126">Related Sections</span></span>  
 [<span data-ttu-id="ce0ba-127">기본 프로그래밍 수명 주기</span><span class="sxs-lookup"><span data-stu-id="ce0ba-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
