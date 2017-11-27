---
title: "쿼리 계획 캐싱(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 814b4451d5e08d5f9df4d370b2127d971f3fdd1d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="query-plan-caching-entity-sql"></a><span data-ttu-id="cd9a7-102">쿼리 계획 캐싱(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="cd9a7-102">Query Plan Caching (Entity SQL)</span></span>
<span data-ttu-id="cd9a7-103">쿼리 실행 시도가 있으면 쿼리 파이프라인에서는 항상 해당 쿼리가 이미 컴파일되어 사용 가능한지 알아보기 위해 쿼리 계획 캐시를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-103">Whenever an attempt to execute a query is made, the query pipeline looks up its query plan cache to see whether the exact query is already compiled and available.</span></span> <span data-ttu-id="cd9a7-104">사용 가능한 쿼리가 있으면 새 쿼리를 작성하지 않고 캐시된 계획을 재사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-104">If so, it reuses the cached plan rather than building a new one.</span></span> <span data-ttu-id="cd9a7-105">쿼리 계획 캐시에 일치 항목이 없을 경우에는 쿼리를 컴파일하고 캐시합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-105">If a match is not found in the query plan cache, the query is compiled and cached.</span></span> <span data-ttu-id="cd9a7-106">쿼리는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 텍스트 및 매개 변수 컬렉션(이름과 형식)으로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-106">A query is identified by its [!INCLUDE[esql](../../../../../../includes/esql-md.md)] text and parameter collection (names and types).</span></span> <span data-ttu-id="cd9a7-107">모든 텍스트 비교에서는 대/소문자가 구별됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-107">All text comparisons are case-sensitive.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="cd9a7-108">구성</span><span class="sxs-lookup"><span data-stu-id="cd9a7-108">Configuration</span></span>  
 <span data-ttu-id="cd9a7-109">쿼리 계획 캐싱은 <xref:System.Data.EntityClient.EntityCommand>를 통해 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-109">Query plan caching is configurable through the <xref:System.Data.EntityClient.EntityCommand>.</span></span>  
  
 <span data-ttu-id="cd9a7-110"><xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>을 통해 쿼리 계획 캐싱을 사용하려면 이 속성을 `true`로, 사용하지 않으려면 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-110">To enable or disable query plan caching through <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, set this property to `true` or `false`.</span></span> <span data-ttu-id="cd9a7-111">두 번 이상 사용할 가능성이 적은 개별 동적 쿼리에 대해 계획 캐싱을 사용하지 않도록 설정하면 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-111">Disabling plan caching for individual dynamic queries that are unlikely to be used more then once improves performance.</span></span>  
  
 <span data-ttu-id="cd9a7-112"><xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>을 통해 쿼리 계획 캐싱을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-112">You can enable query plan caching through <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.</span></span>  
  
## <a name="recommended-practice"></a><span data-ttu-id="cd9a7-113">권장 방법</span><span class="sxs-lookup"><span data-stu-id="cd9a7-113">Recommended Practice</span></span>  
 <span data-ttu-id="cd9a7-114">일반적으로 동적 쿼리는 사용하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-114">Dynamic queries should be avoided, in general.</span></span> <span data-ttu-id="cd9a7-115">다음 동적 쿼리 예제는 유효성 검사 없이 사용자의 직접적인 입력을 사용하므로 SQL 삽입 공격에 취약합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-115">The following dynamic query example is vulnerable to SQL injection attacks, because it takes user input directly without any validation.</span></span>  
  
 `"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;`  
  
 <span data-ttu-id="cd9a7-116">동적으로 생성된 쿼리를 사용하는 경우 다시 사용할 가능성이 적은 캐시 항목의 불필요한 메모리 사용을 방지하기 위해 쿼리 계획 캐싱을 사용하지 않도록 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-116">If you do use dynamically generated queries, consider disabling query plan caching to avoid unnecessary memory consumption for cache entries that are unlikely to be reused.</span></span>  
  
 <span data-ttu-id="cd9a7-117">정적 쿼리 및 매개 변수화된 쿼리에 대해 쿼리 계획 캐싱을 이용하면 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-117">Query plan caching on static queries and parameterized queries can provide performance benefits.</span></span> <span data-ttu-id="cd9a7-118">다음은 정적 쿼리의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-118">The following is an example of a static query:</span></span>  
  
```  
"SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 <span data-ttu-id="cd9a7-119">쿼리가 쿼리 계획 캐시와 제대로 일치하려면 다음 요구 사항을 준수해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-119">For queries to be matched properly by the query plan cache, they should comply with the following requirements:</span></span>  
  
-   <span data-ttu-id="cd9a7-120">쿼리 텍스트가 상수 패턴이어야 하며, 가능한 한 상수 문자열 또는 리소스여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-120">Query text should be a constant pattern, preferably a constant string or a resource.</span></span>  
  
-   <span data-ttu-id="cd9a7-121">사용자가 제공한 값을 전달해야 하는 경우 항상 <xref:System.Data.EntityClient.EntityParameter> 또는 <xref:System.Data.Objects.ObjectParameter>를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-121"><xref:System.Data.EntityClient.EntityParameter> or <xref:System.Data.Objects.ObjectParameter> should be used wherever a user-supplied value must be passed.</span></span>  
  
 <span data-ttu-id="cd9a7-122">쿼리 계획 캐시에서 불필요하게 슬롯을 사용하는 다음 쿼리 패턴을 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd9a7-122">You should avoid the following query patterns, which unnecessarily consume slots in the query plan cache:</span></span>  
  
-   <span data-ttu-id="cd9a7-123">텍스트의 대/소문자 변경</span><span class="sxs-lookup"><span data-stu-id="cd9a7-123">Changes to letter case in the text.</span></span>  
  
-   <span data-ttu-id="cd9a7-124">공백으로 변경</span><span class="sxs-lookup"><span data-stu-id="cd9a7-124">Changes to white space.</span></span>  
  
-   <span data-ttu-id="cd9a7-125">리터럴 값으로 변경</span><span class="sxs-lookup"><span data-stu-id="cd9a7-125">Changes to literal values.</span></span>  
  
-   <span data-ttu-id="cd9a7-126">주석 내부의 텍스트 변경</span><span class="sxs-lookup"><span data-stu-id="cd9a7-126">Changes to text inside comments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd9a7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd9a7-127">See Also</span></span>  
 [<span data-ttu-id="cd9a7-128">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="cd9a7-128">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
