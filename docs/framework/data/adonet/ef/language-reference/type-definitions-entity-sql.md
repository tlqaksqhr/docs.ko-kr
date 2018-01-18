---
title: "형식 정의(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 306b204a-ade5-47ef-95b5-c785d2da4a7e
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3a1321ae85b1f4952334672e7333e80094ad2e31
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="type-definitions-entity-sql"></a><span data-ttu-id="a72a2-102">형식 정의(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="a72a2-102">Type Definitions (Entity SQL)</span></span>
<span data-ttu-id="a72a2-103">형식 정의는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 인라인 함수의 선언문에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-103">A type definition is used in the declaration statement of an [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Inline function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a72a2-104">설명</span><span class="sxs-lookup"><span data-stu-id="a72a2-104">Remarks</span></span>  
 <span data-ttu-id="a72a2-105">인라인 함수의 선언문 이루어져는 [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) 키워드 다음에 괄호 (의 매개 변수 정의 목록 다음에 함수 이름 (예: "MyAvg")를 나타내는 식별자입니다. 예제에서는 "Collection(Decimal)") 했어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-105">The declaration statement for an inline function consists of the [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) keyword followed by the identifier representing the function name (for example, "MyAvg") followed by a parameter definition list in parenthesis (for example, "dues Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="a72a2-106">매개 변수 정의 목록은 0개 이상의 매개 변수 정의로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-106">The parameter definition list consists of zero or more parameter definitions.</span></span> <span data-ttu-id="a72a2-107">각 매개 변수 정의는 식별자("dues"와 같은 함수에 대한 매개 변수 이름)와 뒤에 오는 형식 정의(예: "Collection(Decimal)")로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-107">Each parameter definition consists of an identifier (the name of the parameter to the function, for example, "dues") followed by a type definition (for example, "Collection(Decimal)").</span></span>  
  
 <span data-ttu-id="a72a2-108">형식 정의는 다음 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-108">The type definitions can be either:</span></span>  
  
-   <span data-ttu-id="a72a2-109">식별자 형식(예: "Int32" 또는 "AdventureWorks.Order")</span><span class="sxs-lookup"><span data-stu-id="a72a2-109">The type of the identifier (for example, "Int32" or "AdventureWorks.Order").</span></span>  
  
-   <span data-ttu-id="a72a2-110">`COLLECTION` 키워드와 뒤에 오는 괄호로 묶은 다른 형식 정의(예: "Collection(AdventureWorks.Order)")</span><span class="sxs-lookup"><span data-stu-id="a72a2-110">The keyword `COLLECTION` followed by another type definition in parenthesis (for example, "Collection(AdventureWorks.Order)").</span></span>  
  
-   <span data-ttu-id="a72a2-111">ROW 키워드와 뒤에 오는 괄호로 묶은 속성 정의 목록(예: "Row(x AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="a72a2-111">The keyword ROW followed by a list of property definitions in parenthesis (for example, "Row(x AdventureWorks.Order)").</span></span> <span data-ttu-id="a72a2-112">속성 정의 형식이 같은 "`identifier type_definition`, `identifier type_definition`,...".</span><span class="sxs-lookup"><span data-stu-id="a72a2-112">Property definitions have a format such as "`identifier type_definition`, `identifier type_definition`, ...".</span></span>  
  
-   <span data-ttu-id="a72a2-113">REF 키워드와 뒤에 오는 괄호로 묶은 식별자 형식(예: "Ref(AdventureWorks.Order)").</span><span class="sxs-lookup"><span data-stu-id="a72a2-113">The keyword REF followed by the type of the identifier in parenthesis (for example, "Ref(AdventureWorks.Order)").</span></span> <span data-ttu-id="a72a2-114">REF 형식 정의 연산자의 경우 엔터티 형식을 인수로 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-114">The REF type definition operator requires an entity type as the argument.</span></span> <span data-ttu-id="a72a2-115">기본 형식을 인수로 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-115">You cannot specify a primitive type as the argument.</span></span>  
  
 <span data-ttu-id="a72a2-116">또한 형식 정의를 중첩할 수 있습니다(예: "Collection(Row(x Ref(AdventureWorks.Order)))").</span><span class="sxs-lookup"><span data-stu-id="a72a2-116">You can also nest type definitions (for example, "Collection(Row(x Ref(AdventureWorks.Order)))").</span></span>  
  
 <span data-ttu-id="a72a2-117">형식 정의 옵션은 다음 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-117">The type definition options are:</span></span>  
  
-   <span data-ttu-id="a72a2-118">`IdentifierName supported_type` 또는</span><span class="sxs-lookup"><span data-stu-id="a72a2-118">`IdentifierName supported_type`, or</span></span>  
  
-   <span data-ttu-id="a72a2-119">`IdentifierName` COLLECTION(`type_definition`)</span><span class="sxs-lookup"><span data-stu-id="a72a2-119">`IdentifierName` COLLECTION(`type_definition`), or</span></span>  
  
-   <span data-ttu-id="a72a2-120">`IdentifierName` ROW(`property_definition`)</span><span class="sxs-lookup"><span data-stu-id="a72a2-120">`IdentifierName` ROW(`property_definition`), or</span></span>  
  
-   <span data-ttu-id="a72a2-121">`IdentifierName` REF(`supported_entity_type`)</span><span class="sxs-lookup"><span data-stu-id="a72a2-121">`IdentifierName` REF(`supported_entity_type`)</span></span>  
  
 <span data-ttu-id="a72a2-122">속성 정의 옵션은 `IdentifierName type_definition`입니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-122">The property definition option is `IdentifierName type_definition`.</span></span>  
  
 <span data-ttu-id="a72a2-123">지원되는 형식은 현재 네임스페이스의 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-123">Supported types are any types in the current namespace.</span></span> <span data-ttu-id="a72a2-124">이러한 지원되는 형식에는 기본 형식과 엔터티 형식이 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-124">These include both primitive and entity types.</span></span>  
  
 <span data-ttu-id="a72a2-125">지원되는 엔터티 형식은 현재 네임스페이스의 엔터티 형식만 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-125">Supported entity types refer to only entity types in the current namespace.</span></span> <span data-ttu-id="a72a2-126">이러한 형식에는 기본 형식이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-126">They do not include primitive types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a72a2-127">예제</span><span class="sxs-lookup"><span data-stu-id="a72a2-127">Examples</span></span>  
 <span data-ttu-id="a72a2-128">다음은 간단한 형식 정의의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-128">The following is an example of a simple type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 EDM.Decimal) AS (  
   Round(p1)  
)  
MyRound(CAST(1.7 as EDM.Decimal))  
```  
  
 <span data-ttu-id="a72a2-129">다음은 COLLECTION 형식 정의의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-129">The following is an example of a COLLECTION type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Collection(EDM.Decimal)) AS (  
   Select Round(p1) from p1  
)  
MyRound({CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)})  
```  
  
 <span data-ttu-id="a72a2-130">다음은 ROW 형식 정의의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-130">The following is an example of a ROW type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function MyRound(p1 Row(x EDM.Decimal)) AS (  
   Round(p1.x)  
)  
select MyRound(row(a as x)) from {CAST(1.7 as EDM.Decimal), CAST(2.7 as EDM.Decimal)} as a  
```  
  
 <span data-ttu-id="a72a2-131">다음은 REF 형식 정의의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a72a2-131">The following is an example of a REF type definition.</span></span>  
  
```  
USING Microsoft.Samples.Entity  
Function UnReference(p1 Ref(AdventureWorks.Order)) AS (  
   Deref(p1)  
)  
select Ref(x) from AdventureWorksEntities.SalesOrderHeaders as x  
```  
  
## <a name="see-also"></a><span data-ttu-id="a72a2-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a72a2-132">See Also</span></span>  
 [<span data-ttu-id="a72a2-133">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="a72a2-133">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [<span data-ttu-id="a72a2-134">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="a72a2-134">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
