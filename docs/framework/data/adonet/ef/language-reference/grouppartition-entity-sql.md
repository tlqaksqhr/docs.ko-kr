---
title: GROUPPARTITION(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0482e9b-086c-451c-9dfa-ccb024a9efb6
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 8807564cb9acf8c50aed43ee11441ebdfbbcea78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="grouppartition-entity-sql"></a><span data-ttu-id="e0845-102">GROUPPARTITION(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="e0845-102">GROUPPARTITION (Entity SQL)</span></span>
<span data-ttu-id="e0845-103">집계가 관련된 현재 그룹 파티션에서 예측된 인수 값의 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-103">Returns a collection of argument values that are projected off the current group partition to which the aggregate is related.</span></span> <span data-ttu-id="e0845-104">`GroupPartition` 집계는 그룹 기반 집계이며 컬렉션 기반 형식을 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-104">The `GroupPartition` aggregate is a group-based aggregate and has no collection-based form.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0845-105">구문</span><span class="sxs-lookup"><span data-stu-id="e0845-105">Syntax</span></span>  
  
```  
GROUPPARTITION( [ALL|DISTINCT] expression )  
```  
  
## <a name="arguments"></a><span data-ttu-id="e0845-106">인수</span><span class="sxs-lookup"><span data-stu-id="e0845-106">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="e0845-107">임의의 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식입니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-107">Any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0845-108">설명</span><span class="sxs-lookup"><span data-stu-id="e0845-108">Remarks</span></span>  
 <span data-ttu-id="e0845-109">다음 쿼리는 제품 목록 및 각 제품당 주문 라인 수량 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-109">The following query produces a list of products and a collection of order line quantities per each product:</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="e0845-110">다음 두 쿼리는 구문적으로 서로 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-110">The following two queries are semantically equal:</span></span>  
  
```  
select p, Sum(GroupPartition(ol.Quantity)) from LOB.OrderLines as ol  
  group by ol.Product as p  
select p, Sum(ol.Quantity) from LOB.OrderLines as ol  
  group by ol.Product as p  
```  
  
 <span data-ttu-id="e0845-111">`GROUPPARTITION` 연산자는 사용자 정의 집계 연산자와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-111">The `GROUPPARTITION` operator can be used in conjunction with user-defined aggregate functions.</span></span>  
  
 <span data-ttu-id="e0845-112">`GROUPPARTITION` 은 그룹화된 입력 집합에 대한 참조를 포함하는 특수 집계 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-112">`GROUPPARTITION` is a special aggregate operator that holds a reference to the grouped input set.</span></span> <span data-ttu-id="e0845-113">이러한 참조는 범위 내에 GROUP BY가 있는 쿼리의 아무 곳에서나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-113">This reference can be used anywhere in the query where GROUP BY is in scope.</span></span> <span data-ttu-id="e0845-114">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-114">For example,</span></span>  
  
```  
select p, GroupPartition(ol.Quantity) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="e0845-115">일반 GROUP BY를 사용하는 경우 그룹화 결과는 숨겨집니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-115">With a regular GROUP BY, the results of the grouping are hidden.</span></span> <span data-ttu-id="e0845-116">결과는 집계 함수에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-116">You can only use the results in an aggregate function.</span></span> <span data-ttu-id="e0845-117">그룹화 결과를 보려면 하위 쿼리를 사용하여 그룹화 및 입력 집합 결과를 상호 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-117">In order to see the results of the grouping, you have to correlate the results of the grouping and the input set by using a subquery.</span></span> <span data-ttu-id="e0845-118">다음 두 쿼리는 동일한 의미를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-118">The following two queries are equivalent:</span></span>  
  
```  
select p, (select q from GroupPartition(ol.Quantity) as q) from LOB.OrderLines as ol group by ol.Product as p  
select p, (select ol.Quantity as q from LOB.OrderLines as ol2 where ol2.Product = p) from LOB.OrderLines as ol group by ol.Product as p  
```  
  
 <span data-ttu-id="e0845-119">예제와 나와 있듯이 GROUPPARTITION 집계 연산자를 사용하면 그룹화 이후 입력 집합에 대한 참조를 보다 쉽게 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-119">As seen from the example, the GROUPPARTITION aggregate operator makes it easier to get a reference to the input set after the grouping.</span></span>  
  
 <span data-ttu-id="e0845-120">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 매개 변수를 사용하는 경우 GROUPPARTITION 연산자는 연산자 입력에서 `expression` 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-120">The GROUPPARTITION operator can specify any [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression in the operator input when you use the `expression` parameter.</span></span>  
  
 <span data-ttu-id="e0845-121">예를 들어, 그룹 파티션에 대한 다음의 모든 입력 식은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-121">For instance all of the following input expressions to the group partition are valid:</span></span>  
  
```  
select groupkey, GroupPartition(b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(1) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(a + b) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({a + b}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition({42}) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
select groupkey, GroupPartition(b > a) from {1,2,3} as a inner join {4,5,6} as b on true group by a as groupkey  
```  
  
## <a name="example"></a><span data-ttu-id="e0845-122">예</span><span class="sxs-lookup"><span data-stu-id="e0845-122">Example</span></span>  
 <span data-ttu-id="e0845-123">다음 예제에서는 GROUPPARTITION 절을 GROUP BY 절과 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-123">The following example shows how to use the GROUPPARTITION clause with the GROUP BY clause.</span></span> <span data-ttu-id="e0845-124">GROUP BY 절은 `SalesOrderHeader` 엔터티를 해당 `Contact`별로 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-124">The GROUP BY clause groups `SalesOrderHeader` entities by their `Contact`.</span></span> <span data-ttu-id="e0845-125">그리고 나서 GROUPPARTITION 절은 각 그룹에 대한 `TotalDue` 속성을 예상하여 10진수 컬렉션을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e0845-125">The GROUPPARTITION clause then projects the `TotalDue` property for each group, resulting in a collection of decimals.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]
