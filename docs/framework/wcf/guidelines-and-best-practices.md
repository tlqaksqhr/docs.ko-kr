---
title: "지침 및 최선의 구현 방법"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, guidelines
- best practices [WCF], application design
- Windows Communication Foundation, best practices
- WCF, best practices
- Windows Communication Foundation, guidelines
ms.assetid: 5098ba46-6e8d-4e02-b0c5-d737f9fdad84
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 978cb7dcfd132ea253fcb5f13174e14c7341f11a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="guidelines-and-best-practices"></a><span data-ttu-id="1ae75-102">지침 및 최선의 구현 방법</span><span class="sxs-lookup"><span data-stu-id="1ae75-102">Guidelines and Best Practices</span></span>
<span data-ttu-id="1ae75-103">이 단원의 항목에서는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만들기 위한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-103">This section contains topics that provide guidelines for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ae75-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="1ae75-104">In This Section</span></span>  
 [<span data-ttu-id="1ae75-105">모범 사례: 데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="1ae75-105">Best Practices: Data Contract Versioning</span></span>](../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 <span data-ttu-id="1ae75-106">다음 버전 생성 시 손상되지 않는 데이터 계약을 만드는 방법 및 시점에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-106">Explains how and when to create data contracts that do not break when future versions are created.</span></span>  
  
 [<span data-ttu-id="1ae75-107">서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="1ae75-107">Service Versioning</span></span>](../../../docs/framework/wcf/service-versioning.md)  
 <span data-ttu-id="1ae75-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 버전 관리를 고려하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-108">Explains how to consider versioning in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="1ae75-109">예를 들어, 배포 후 서비스(및 노출된 끝점)를 비즈니스 요구 사항 또는 IT 요구 사항 변경을 충족하거나 문제를 해결하기 위해 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-109">After deployment, services (and the endpoints they expose) might need to be changed, for example, to satisfy changing business requirements or IT requirements, or to fix issues.</span></span> <span data-ttu-id="1ae75-110">각 변경 작업에는 새 버전의 서비스가 도입됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-110">Each change introduces a new version of the service.</span></span>  
  
 [<span data-ttu-id="1ae75-111">부하 분산</span><span class="sxs-lookup"><span data-stu-id="1ae75-111">Load Balancing</span></span>](../../../docs/framework/wcf/load-balancing.md)  
 <span data-ttu-id="1ae75-112">웹 팜에서 부하 분산을 위한 지침을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-112">Lists guidelines for load balancing with a Web farm.</span></span>  
  
 [<span data-ttu-id="1ae75-113">리소스 사용 제어 및 성능 향상</span><span class="sxs-lookup"><span data-stu-id="1ae75-113">Controlling Resource Consumption and Improving Performance</span></span>](../../../docs/framework/wcf/controlling-resource-consumption-and-improving-performance.md)  
 <span data-ttu-id="1ae75-114">과도한 리소스 사용을 방지하고 보안을 향상시키는 데 도움을 주도록 디자인된 속성에 대해 설명하고, 이러한 속성 사용에 대한 자세한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-114">Describes the properties that are designed to help prevent undue resource consumption and improve security and points to more complete information about their use.</span></span>  
  
 [<span data-ttu-id="1ae75-115">ClickOnce를 사용하여 WCF 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="1ae75-115">Deploying WCF Applications with ClickOnce</span></span>](../../../docs/framework/wcf/deploying-wcf-applications-with-clickonce.md)  
 <span data-ttu-id="1ae75-116">ClickOnce 기능 사용 시 고려할 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1ae75-116">Describes the considerations to be made when using the ClickOnce feature.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1ae75-117">참조</span><span class="sxs-lookup"><span data-stu-id="1ae75-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="1ae75-118">관련 단원</span><span class="sxs-lookup"><span data-stu-id="1ae75-118">Related Sections</span></span>  
 [<span data-ttu-id="1ae75-119">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="1ae75-119">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="1ae75-120">기본 WCF 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="1ae75-120">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ae75-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ae75-121">See Also</span></span>  
 [<span data-ttu-id="1ae75-122">Windows Communication Foundation 정의</span><span class="sxs-lookup"><span data-stu-id="1ae75-122">What Is Windows Communication Foundation</span></span>](../../../docs/framework/wcf/whats-wcf.md)  
 [<span data-ttu-id="1ae75-123">Windows Communication Foundation 샘플</span><span class="sxs-lookup"><span data-stu-id="1ae75-123">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
 [<span data-ttu-id="1ae75-124">개념적 개요</span><span class="sxs-lookup"><span data-stu-id="1ae75-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="1ae75-125">클라이언트 빌드</span><span class="sxs-lookup"><span data-stu-id="1ae75-125">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)
