---
title: "방법: 리플렉션 공급자 사용하여 데이터 서비스 만들기(WCF Data Services)"
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
helpviewer_keywords: WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 343fc6043b4cfc7ea02ff33c18aaaf5ced14c11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="d9f17-102">방법: 리플렉션 공급자 사용하여 데이터 서비스 만들기(WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="d9f17-102">How to: Create a Data Service Using the Reflection Provider (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="d9f17-103">를 사용하면 클래스가 <xref:System.Linq.IQueryable%601> 인터페이스를 구현하는 개체로 노출되는 한 임의의 클래스를 기반으로 하여 데이터 모델을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-103"> enables you to define a data model that is based on arbitrary classes as long as those classes are exposed as objects that implement the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="d9f17-104">자세한 내용은 참조 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-104">For more information, see [Data Services Providers](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9f17-105">예</span><span class="sxs-lookup"><span data-stu-id="d9f17-105">Example</span></span>  
 <span data-ttu-id="d9f17-106">다음 예제에서는 `Orders` 및 `Items`가 포함된 데이터 모델을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-106">The following example defines a data model that includes `Orders` and `Items`.</span></span> <span data-ttu-id="d9f17-107">엔터티 컨테이너 클래스 `OrderItemData`에는 <xref:System.Linq.IQueryable%601> 인터페이스를 반환하는 두 개의 공용 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-107">The entity container class `OrderItemData` has two public methods that return <xref:System.Linq.IQueryable%601> interfaces.</span></span> <span data-ttu-id="d9f17-108">이러한 인터페이스는 `Orders` 및 `Items` 엔터티 형식의 엔터티 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-108">These interfaces are the entity sets of the `Orders` and `Items` entity types.</span></span> <span data-ttu-id="d9f17-109">`Order`에는 여러 `Items`가 포함될 수 있으므로 `Orders` 엔터티 형식의 `Items` 탐색 속성은 `Items` 개체의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-109">An `Order` can include multiple `Items`, so the `Orders` entity type has an `Items` navigation property that returns a collection of `Items` objects.</span></span> <span data-ttu-id="d9f17-110">`OrderItemData` 엔터티 컨테이너 클래스는 <xref:System.Data.Services.DataService%601> 데이터 서비스가 파생되는 `OrderItems` 클래스의 제네릭 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-110">The `OrderItemData` entity container class is the generic type of the <xref:System.Data.Services.DataService%601> class from which the `OrderItems` data service is derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d9f17-111">이 예제에서는 메모리 내 데이터 공급자를 보여 주며 변경 내용이 현재 개체 인스턴스 외부에서 유지되지 않으므로 <xref:System.Data.Services.IUpdatable> 인터페이스를 구현해도 파생되는 이점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-111">Because this example demonstrates an in-memory data provider and changes are not persisted outside of the current object instances, there is no benefit derived from implementing the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="d9f17-112">구현 하는 예제는 <xref:System.Data.Services.IUpdatable> 인터페이스를 참조 [하는 방법: LINQ to SQL 데이터 원본을 사용 하 여 데이터 서비스 만들기](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f17-112">For an example that implements the <xref:System.Data.Services.IUpdatable> interface, see [How to: Create a Data Service Using a LINQ to SQL Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).</span></span>  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a><span data-ttu-id="d9f17-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9f17-113">See Also</span></span>  
 [<span data-ttu-id="d9f17-114">방법: LINQ to SQL 데이터 원본을 사용하여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="d9f17-114">How to: Create a Data Service Using a LINQ to SQL Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)  
 [<span data-ttu-id="d9f17-115">Data Services 공급자</span><span class="sxs-lookup"><span data-stu-id="d9f17-115">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="d9f17-116">방법: ADO.NET Entity Framework 데이터 원본을 사용하여 데이터 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="d9f17-116">How to: Create a Data Service Using an ADO.NET Entity Framework Data Source</span></span>](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
