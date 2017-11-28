---
title: "메서드 기반 쿼리 구문 예제: 관계 탐색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c7c5e1c17fbb0758cc395b6a76b7c0d1065be04a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="0ae87-102">메서드 기반 쿼리 구문 예제: 관계 탐색</span><span class="sxs-lookup"><span data-stu-id="0ae87-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="0ae87-103">[!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]의 탐색 속성은 연결의 End에서 엔터티를 찾는 데 사용되는 바로 가기 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="0ae87-104">탐색 속성을 사용하면 엔터티 간에 탐색하거나 연결 집합을 통해 관련 엔터티 간에 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="0ae87-105">이 항목에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에서 탐색 속성을 통해 관계를 탐색하는 방법을 보여 주는 메서드 기반 쿼리 구문 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="0ae87-106">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0ae87-107">이 항목의 예제에서 다음을 사용 하 여 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="0ae87-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="0ae87-108">예제</span><span class="sxs-lookup"><span data-stu-id="0ae87-108">Example</span></span>  
 <span data-ttu-id="0ae87-109">메서드 기반 쿼리 구문을 사용하는 다음 예제에서는 <xref:System.Linq.Queryable.SelectMany%2A> 메서드를 사용하여 성이 "Zhou"인 연락처의 모든 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="0ae87-110">`Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 `SalesOrderHeader` 개체 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="0ae87-111">예제</span><span class="sxs-lookup"><span data-stu-id="0ae87-111">Example</span></span>  
 <span data-ttu-id="0ae87-112">메서드 기반 쿼리 구문을 사용하는 다음 예제에서는 <xref:System.Linq.Queryable.Select%2A> 메서드를 사용하여 성이 "Zhou"인 각 연락처의 총 금액 합계와 연락처 ID를 모두 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="0ae87-113">`Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 `SalesOrderHeader` 개체 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="0ae87-114">`Sum` 메서드는 `Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 모든 주문에 대한 총 금액을 더합니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="0ae87-115">예제</span><span class="sxs-lookup"><span data-stu-id="0ae87-115">Example</span></span>  
 <span data-ttu-id="0ae87-116">메서드 기반 쿼리 구문의 다음 예제에서는 성이 "Zhou"인 연락처의 모든 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="0ae87-117">`Contact.SalesOrderHeader` 탐색 속성을 사용하여 각 연락처의 `SalesOrderHeader` 개체 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="0ae87-118">연락처의 이름과 주문은 익명 형식으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="0ae87-119">예제</span><span class="sxs-lookup"><span data-stu-id="0ae87-119">Example</span></span>  
 <span data-ttu-id="0ae87-120">다음 예제에서는 `SalesOrderHeader.Address` 및 `SalesOrderHeader.Contact` 탐색 속성을 사용하여 서로 연결된 `Address` 및 `Contact` 개체의 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="0ae87-121">Seattle 시로 가는 각 주문에 대한 연락처의 성, 주소, 판매 주문 번호 및 총 주문 금액이 익명 형식으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="0ae87-122">예제</span><span class="sxs-lookup"><span data-stu-id="0ae87-122">Example</span></span>  
 <span data-ttu-id="0ae87-123">다음 예제에서는 `Where` 메서드를 사용하여 2003년 12월 1일 이후의 주문을 찾은 다음 `order.SalesOrderDetail` 탐색 속성을 사용하여 각 주문의 세부 사항을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0ae87-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="0ae87-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ae87-124">See Also</span></span>  
 [<span data-ttu-id="0ae87-125">탐색 속성</span><span class="sxs-lookup"><span data-stu-id="0ae87-125">Navigation Properties</span></span>](http://msdn.microsoft.com/en-us/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
 [<span data-ttu-id="0ae87-126">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="0ae87-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
