---
title: "정식 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbcc9928-36ea-4dff-9e31-96549ffed958
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: da48efc110669c170fc409e22cb8402f471b22e7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="canonical-functions"></a><span data-ttu-id="bb541-102">정식 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-102">Canonical Functions</span></span>
<span data-ttu-id="bb541-103">이 단원에서는 모든 데이터 공급자에서 지원되며 모든 쿼리 기술에 사용될 수 있는 정식 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-103">This section discusses canonical functions that are supported by all data providers, and can be used by all querying technologies.</span></span> <span data-ttu-id="bb541-104">정식 함수는 공급자에서 확장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-104">Canonical functions cannot be extended by a provider.</span></span>  
  
 <span data-ttu-id="bb541-105">이러한 정식 함수는 공급자에 해당하는 데이터 소스 기능으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-105">These canonical functions will be translated to the corresponding data source functionality for the provider.</span></span> <span data-ttu-id="bb541-106">그러면 다양한 데이터 소스에서 일반적인 형태로 함수 호출을 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-106">This allows for function invocations expressed in a common form across data sources.</span></span>  
  
 <span data-ttu-id="bb541-107">이러한 정식 함수는 데이터 소스에 대해 독립적이므로, 정식 함수의 인수와 반환 형식은 개념적 모델의 형식으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-107">Because these canonical functions are independent of data sources, argument and return types of canonical functions are defined in terms of types in the conceptual model.</span></span> <span data-ttu-id="bb541-108">하지만 일부 데이터 소스에서는 개념적 모델의 모든 형식이 지원되지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-108">However, some data sources might not support all types in the conceptual model.</span></span>  
  
 <span data-ttu-id="bb541-109">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서 정식 함수를 사용하면 데이터 소스에서 적절한 함수가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-109">When canonical functions are used in an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query, the appropriate function will be called at the data source.</span></span>  
  
 <span data-ttu-id="bb541-110">모든 정규 함수에는 null 입력 동작과 오류 조건이 모두 명시적으로 지정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-110">All canonical functions have both null-input behavior and error conditions explicitly specified.</span></span> <span data-ttu-id="bb541-111">이런 동작을 저장소 공급자에서 준수해야 하지만, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에서 이 동작을 적용하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-111">Store providers should comply with that behavior, but [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not enforce this behavior.</span></span>  
  
 <span data-ttu-id="bb541-112">LINQ 시나리오의 경우, [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에 대한 쿼리에서 CLR 메서드를 기본 데이터 소스의 메서드에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-112">For LINQ scenarios, queries against the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] involve mapping CLR methods to methods in the underlying data source.</span></span> <span data-ttu-id="bb541-113">CLR 메서드는 특정 메서드 집합이 데이터 소스에 관계없이 올바르게 매핑되도록 정식 함수에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-113">The CLR methods map to canonical functions, so that a specific set of methods will correctly map, regardless of the data source.</span></span>  
  
## <a name="canonical-functions-namespace"></a><span data-ttu-id="bb541-114">정식 함수 네임스페이스</span><span class="sxs-lookup"><span data-stu-id="bb541-114">Canonical Functions Namespace</span></span>  
 <span data-ttu-id="bb541-115">정식 함수의 네임스페이스는 <xref:System.Data.Metadata.Edm>입니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-115">The namespace for canonical function is <xref:System.Data.Metadata.Edm>.</span></span> <span data-ttu-id="bb541-116"><xref:System.Data.Metadata.Edm> 네임스페이스는 모든 쿼리에 자동으로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-116">The <xref:System.Data.Metadata.Edm> namespace is automatically included in all queries.</span></span> <span data-ttu-id="bb541-117">하지만, 정식 함수와 이름이 같은 함수가 포함된(<xref:System.Data.Metadata.Edm> 네임스페이스) 다른 네임스페이스를 가져온 경우 네임스페이스를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-117">However, if another namespace is imported that contains a function with the same name as a canonical function (in the <xref:System.Data.Metadata.Edm> namespace), you must specify the namespace.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb541-118">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="bb541-118">In This Section</span></span>  
 [<span data-ttu-id="bb541-119">집계 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-119">Aggregate Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)  
 <span data-ttu-id="bb541-120">집계 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-120">Discusses aggregate [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="bb541-121">수학 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-121">Math Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/math-canonical-functions.md)  
 <span data-ttu-id="bb541-122">수식 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-122">Discusses math [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="bb541-123">문자열 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-123">String Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/string-canonical-functions.md)  
 <span data-ttu-id="bb541-124">문자열 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-124">Discusses string [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="bb541-125">날짜 및 시간 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-125">Date and Time Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/date-and-time-canonical-functions.md)  
 <span data-ttu-id="bb541-126">날짜 및 시간 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-126">Discusses date and time [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="bb541-127">비트 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-127">Bitwise Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/bitwise-canonical-functions.md)  
 <span data-ttu-id="bb541-128">비트 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-128">Discusses bitwise [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="bb541-129">공간 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-129">Spatial Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/spatial-functions.md)  
 <span data-ttu-id="bb541-130">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 공간 정식 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-130">Discusses Spatial [!INCLUDE[esql](../../../../../../includes/esql-md.md)] canonical functions.</span></span>  
  
 [<span data-ttu-id="bb541-131">기타 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-131">Other Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/other-canonical-functions.md)  
 <span data-ttu-id="bb541-132">비트, 날짜/시간, 문자열, 수식, 집계 등으로 분류되지 않는 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bb541-132">Discusses functions not classified as bitwise, date/time, string, math, or aggregate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb541-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb541-133">See Also</span></span>  
 [<span data-ttu-id="bb541-134">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="bb541-134">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="bb541-135">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="bb541-135">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="bb541-136">개념적 모델 정식 함수와 SQL Server 함수 매핑</span><span class="sxs-lookup"><span data-stu-id="bb541-136">Conceptual Model Canonical to SQL Server Functions Mapping</span></span>](../../../../../../docs/framework/data/adonet/ef/conceptual-model-canonical-to-sql-server-functions-mapping.md)  
 [<span data-ttu-id="bb541-137">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="bb541-137">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)
