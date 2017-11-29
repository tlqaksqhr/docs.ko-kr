---
title: "방법: 서비스 작업 정의(WCF Data Services)"
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
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: feac51c92a7e963d440eefbae94a58b94f49797e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a><span data-ttu-id="cb9a2-102">방법: 서비스 작업 정의(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="cb9a2-102">How to: Define a Service Operation (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="cb9a2-103">는 서버에서 서비스 작업으로 정의된 메서드를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-103"> expose methods that are defined on the server as service operations.</span></span> <span data-ttu-id="cb9a2-104">서비스 작업 URI는 서버에 정의 하는 메서드를 통해 액세스를 제공 하는 데이터 서비스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-104">Service operations allow a data service to provide access through a URI to a method that is defined on the server.</span></span> <span data-ttu-id="cb9a2-105">서비스 작업을 정의 하려면 적용 된 [`WebGet]` 또는 `[WebInvoke]` 특성을 메서드에 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-105">To define a service operation, apply the [`WebGet]` or `[WebInvoke]` attribute to the method.</span></span> <span data-ttu-id="cb9a2-106">쿼리 연산자를 지원 하려면 서비스 작업을 반환 해야 합니다는 <xref:System.Linq.IQueryable%601> 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-106">To support query operators, the service operation must return an <xref:System.Linq.IQueryable%601> instance.</span></span> <span data-ttu-id="cb9a2-107">서비스 작업은 <xref:System.Data.Services.DataService%601.CurrentDataSource%2A>의 <xref:System.Data.Services.DataService%601> 속성을 통해 기본 데이터 소스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-107">Service operations may access the underlying data source through the <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> property on the <xref:System.Data.Services.DataService%601>.</span></span> <span data-ttu-id="cb9a2-108">자세한 내용은 참조 [서비스 작업](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-108">For more information, see [Service Operations](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="cb9a2-109">이 항목의 예제에서는 `GetOrdersByCity`의 필터링된 <xref:System.Linq.IQueryable%601> 인스턴스 및 관련 `Orders` 개체를 반환하는 `Order_Details`라는 서비스 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-109">The example in this topic defines a service operation named `GetOrdersByCity` that returns a filtered <xref:System.Linq.IQueryable%601> instance of `Orders` and related `Order_Details` objects.</span></span> <span data-ttu-id="cb9a2-110">이 예제에서는 Northwind 샘플 데이터 서비스의 데이터 소스인 <xref:System.Data.Objects.ObjectContext> 인스턴스에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-110">The example accesses the <xref:System.Data.Objects.ObjectContext> instance that is the data source for the Northwind sample data service.</span></span> <span data-ttu-id="cb9a2-111">이 서비스를 완료할 때 만드는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-111">This service is created when you complete the [WCF Data Services quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a><span data-ttu-id="cb9a2-112">Northwind 데이터 서비스에 서비스 작업을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="cb9a2-112">To define a service operation in the Northwind data service</span></span>  
  
1.  <span data-ttu-id="cb9a2-113">Northwind 데이터 서비스 프로젝트에서 Northwind.svc 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-113">In the Northwind data service project, open the Northwind.svc file.</span></span>  
  
2.  <span data-ttu-id="cb9a2-114">`Northwind` 클래스에서 `GetOrdersByCity`라는 서비스 작업 메서드를 다음과 같이 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-114">In the `Northwind` class, define a service operation method named `GetOrdersByCity` as follows:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  <span data-ttu-id="cb9a2-115">`InitializeService` 클래스의 `Northwind` 메서드에서 다음 코드를 추가하여 서비스 작업에 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-115">In the `InitializeService` method of the `Northwind` class, add the following code to enable access to the service operation:</span></span>  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a><span data-ttu-id="cb9a2-116">GetOrdersByCity 서비스 작업을 쿼리하려면</span><span class="sxs-lookup"><span data-stu-id="cb9a2-116">To query the GetOrdersByCity service operation</span></span>  
  
-   <span data-ttu-id="cb9a2-117">웹 브라우저에서 다음 URI 중 하나를 입력하여 다음 예제에 정의된 서비스 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-117">In a Web browser, enter one of the following URIs to invoke the service operation that is defined in the following example:</span></span>  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a><span data-ttu-id="cb9a2-118">예제</span><span class="sxs-lookup"><span data-stu-id="cb9a2-118">Example</span></span>  
 <span data-ttu-id="cb9a2-119">다음 예제에서는 Northwind 데이터 서비스에 `GetOrderByCity`라는 서비스 작업을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-119">The following example implements a service operation named `GetOrderByCity` on the Northwind data service.</span></span> <span data-ttu-id="cb9a2-120">이 작업은 ADO.NET Entity Framework를 사용하여 제공된 도시 이름을 기준으로 `Orders` 집합 및 관련 `Order_Details` 개체를 <xref:System.Linq.IQueryable%601> 인스턴스로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-120">This operation uses the ADO.NET Entity Framework to return a set of `Orders` and related `Order_Details` objects as an <xref:System.Linq.IQueryable%601> instance based on the provided city name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb9a2-121">메서드에서 <xref:System.Linq.IQueryable%601> 인스턴스를 반환하기 때문에 이 서비스 작업 끝점에서 쿼리 연산자가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb9a2-121">Query operators are supported on this service operation endpoint because the method returns an <xref:System.Linq.IQueryable%601> instance.</span></span>  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a><span data-ttu-id="cb9a2-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb9a2-122">See Also</span></span>  
 [<span data-ttu-id="cb9a2-123">WCF Data Services 정의</span><span class="sxs-lookup"><span data-stu-id="cb9a2-123">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
