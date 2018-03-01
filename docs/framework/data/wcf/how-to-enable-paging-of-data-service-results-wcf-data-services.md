---
title: "방법: 데이터 서비스 결과의 페이징 사용(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b03dd234681d031361696108702a7bbb558065ef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a><span data-ttu-id="8d988-102">방법: 데이터 서비스 결과의 페이징 사용(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="8d988-102">How to: Enable Paging of Data Service Results (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="8d988-103">를 사용하면 데이터 서비스 쿼리에서 반환되는 엔터티 수를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-103"> enables you to limit the number of entities returned by a data service query.</span></span> <span data-ttu-id="8d988-104">페이지 제한은 서비스가 초기화될 때 호출되는 메서드에서 정의되며 각 엔터티 집합에 대해 별도로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-104">Page limits are defined in the method that is called when the service is initialized and can be set separately for each entity set.</span></span>  
  
 <span data-ttu-id="8d988-105">페이징을 사용하도록 설정하면 피드의 최종 항목에 다음 데이터 페이지에 대한 링크가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-105">When paging is enabled, the final entry in the feed contains a link to the next page of data.</span></span> <span data-ttu-id="8d988-106">자세한 내용은 참조 [데이터 서비스 구성](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-106">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="8d988-107">이 항목에서는 데이터 서비스를 수정하여 반환된 `Customers` 및 `Orders` 엔터티 집합의 페이징을 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-107">This topic shows how to modify a data service to enable paging of returned `Customers` and `Orders` entity sets.</span></span> <span data-ttu-id="8d988-108">이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-108">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="8d988-109">이 서비스를 완료할 때 만드는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-109">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a><span data-ttu-id="8d988-110">반환된 Customers 및 Orders 엔터티 집합의 페이징을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="8d988-110">How to enable paging of returned Customers and Orders entity sets</span></span>  
  
-   <span data-ttu-id="8d988-111">데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8d988-111">In the code for the data service, replace the placeholder code in the `InitializeService` function with the following:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a><span data-ttu-id="8d988-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d988-112">See Also</span></span>  
 [<span data-ttu-id="8d988-113">지연 콘텐츠 로드</span><span class="sxs-lookup"><span data-stu-id="8d988-113">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 [<span data-ttu-id="8d988-114">방법: 페이지 단위 결과 로드</span><span class="sxs-lookup"><span data-stu-id="8d988-114">How to: Load Paged Results</span></span>](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
