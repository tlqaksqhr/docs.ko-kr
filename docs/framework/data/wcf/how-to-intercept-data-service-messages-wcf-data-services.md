---
title: "방법: 데이터 서비스 메시지 가로채기(WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6c18664eaa154fbc048c77cb359d0926f04b7e52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a><span data-ttu-id="9cd32-102">방법: 데이터 서비스 메시지 가로채기(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="9cd32-102">How to: Intercept Data Service Messages (WCF Data Services)</span></span>
<span data-ttu-id="9cd32-103">[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하면 사용자 지정 논리를 작업에 추가할 수 있도록 요청 메시지를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-103">With [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], you can intercept request messages so that you can add custom logic to an operation.</span></span> <span data-ttu-id="9cd32-104">메시지를 가로채기 위해 데이터 서비스에서 특별 한 특성이 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-104">To intercept a message, you use specially attributed methods in the data service.</span></span> <span data-ttu-id="9cd32-105">자세한 내용은 참조 [인터셉터](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-105">For more information, see [Interceptors](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="9cd32-106">이 항목의 예제에서는 Northwind 샘플 데이터 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-106">The example in this topic uses the Northwind sample data service.</span></span> <span data-ttu-id="9cd32-107">이 서비스를 완료할 때 만드는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-107">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a><span data-ttu-id="9cd32-108">Orders 엔터티 집합에 대해 쿼리 인터셉터를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9cd32-108">To define a query interceptor for the Orders entity set</span></span>  
  
1.  <span data-ttu-id="9cd32-109">Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-109">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="9cd32-110">`Northwind` 클래스의 코드 페이지에서 다음 `using` 문(Visual Basic에서는 `Imports`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-110">In the code page for the `Northwind` class, add the following `using` statement (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  <span data-ttu-id="9cd32-111">`Northwind` 클래스에서 `OnQueryOrders`라는 서비스 작업 메서드를 다음과 같이 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-111">In the `Northwind` class, define a service operation method named `OnQueryOrders` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a><span data-ttu-id="9cd32-112">Products 엔터티 집합에 대해 변경 인터셉터를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="9cd32-112">To define a change interceptor for the Products entity set</span></span>  
  
1.  <span data-ttu-id="9cd32-113">Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="9cd32-114">`Northwind` 클래스에서 `OnChangeProducts`라는 서비스 작업 메서드를 다음과 같이 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-114">In the `Northwind` class, define a service operation method named `OnChangeProducts` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a><span data-ttu-id="9cd32-115">예제</span><span class="sxs-lookup"><span data-stu-id="9cd32-115">Example</span></span>  
 <span data-ttu-id="9cd32-116">다음 예제에서는 `Orders` 엔터티 집합에 대해 람다 식을 반환하는 쿼리 인터셉터 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-116">This example defines a query interceptor method for the `Orders` entity set that returns a lambda expression.</span></span> <span data-ttu-id="9cd32-117">이 식에는 특정 연락처 이름이 있는 관련 `Orders`를 기반으로 요청된 `Customers`를 필터링하는 대리자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-117">This expression contains a delegate that filters the requested `Orders` based on related `Customers` that have a specific contact name.</span></span> <span data-ttu-id="9cd32-118">이름은 요청하는 사용자를 기반으로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-118">The name is in turn determined based on the requesting user.</span></span> <span data-ttu-id="9cd32-119">이 예제에서는 WCF를 사용하고 인증이 사용하도록 설정된 ASP.NET 웹 응용 프로그램 내에 데이터 서비스가 호스트된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-119">This example assumes that the data service is hosted within an ASP.NET Web application that uses WCF, and that authentication is enabled.</span></span> <span data-ttu-id="9cd32-120"><xref:System.Web.HttpContext> 클래스는 현재 요청의 사용자를 검색하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-120">The <xref:System.Web.HttpContext> class is used to retrieve the principle of the current request.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a><span data-ttu-id="9cd32-121">예제</span><span class="sxs-lookup"><span data-stu-id="9cd32-121">Example</span></span>  
 <span data-ttu-id="9cd32-122">다음 예제에서는 `Products` 엔터티 집합에 대해 변경 인터셉터 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-122">This example defines a change interceptor method for the `Products` entity set.</span></span> <span data-ttu-id="9cd32-123">이 메서드는 <xref:System.Data.Services.UpdateOperations.Add> 또는 <xref:System.Data.Services.UpdateOperations.Change> 작업에 대해 서비스 입력의 유효성을 검사하고 판매가 중단된 제품이 변경되는 경우 예외를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-123">This method validates input to the service for an <xref:System.Data.Services.UpdateOperations.Add> or <xref:System.Data.Services.UpdateOperations.Change> operation and raises an exception if a change is being made to a discontinued product.</span></span> <span data-ttu-id="9cd32-124">또한 제품 삭제를 지원되지 않는 작업으로 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="9cd32-124">It also blocks the deletion of products as an unsupported operation.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a><span data-ttu-id="9cd32-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9cd32-125">See Also</span></span>  
 [<span data-ttu-id="9cd32-126">방법: 서비스 작업 정의</span><span class="sxs-lookup"><span data-stu-id="9cd32-126">How to: Define a Service Operation</span></span>](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)  
 [<span data-ttu-id="9cd32-127">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="9cd32-127">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
