---
title: LIKE(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8300e6d2-875b-481e-9ef4-e1e7c12d46fa
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f7118637671dbc18c1385b71cc492b5307a377c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="like-entity-sql"></a><span data-ttu-id="938f5-102">LIKE(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="938f5-102">LIKE (Entity SQL)</span></span>
<span data-ttu-id="938f5-103">특정 문자 `String`이 지정된 패턴과 일치하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-103">Determines whether a specific character `String` matches a specified pattern.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="938f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="938f5-104">Syntax</span></span>  
  
```  
match [NOT] LIKE pattern [ESCAPE escape]  
```  
  
## <a name="arguments"></a><span data-ttu-id="938f5-105">인수</span><span class="sxs-lookup"><span data-stu-id="938f5-105">Arguments</span></span>  
 `match`  
 <span data-ttu-id="938f5-106">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 값을 반환하는 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-106">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expression that evaluates to a `String`.</span></span>  
  
 `pattern`  
 <span data-ttu-id="938f5-107">지정된 `String`과 일치하는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-107">A pattern to match to the specified `String`.</span></span>  
  
 `escape`  
 <span data-ttu-id="938f5-108">이스케이프 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-108">An escape character.</span></span>  
  
 <span data-ttu-id="938f5-109">NOT</span><span class="sxs-lookup"><span data-stu-id="938f5-109">NOT</span></span>  
 <span data-ttu-id="938f5-110">LIKE의 결과를 부정하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-110">Specifies that the result of LIKE be negated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="938f5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="938f5-111">Return Value</span></span>  
 <span data-ttu-id="938f5-112">`true`이 패턴과 일치하면 `string`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-112">`true` if the `string` matches the pattern; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="938f5-113">설명</span><span class="sxs-lookup"><span data-stu-id="938f5-113">Remarks</span></span>  
 <span data-ttu-id="938f5-114">LIKE 연산자를 사용하는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식의 계산은 같음을 필터 조건으로 사용하는 식과 동일한 방법으로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-114">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] expressions that use the LIKE operator are evaluated in much the same way as expressions that use equality as the filter criteria.</span></span> <span data-ttu-id="938f5-115">하지만, LIKE 연산자를 사용하는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식에는 리터럴과 와일드카드 문자 모두가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-115">However, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] expressions that use the LIKE operator can include both literals and wildcard characters.</span></span>  
  
 <span data-ttu-id="938f5-116">다음 표에서는 패턴 `string`의 구문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-116">The following table describes the syntax of the pattern `string`.</span></span>  
  
|<span data-ttu-id="938f5-117">와일드카드 문자</span><span class="sxs-lookup"><span data-stu-id="938f5-117">Wildcard Character</span></span>|<span data-ttu-id="938f5-118">설명</span><span class="sxs-lookup"><span data-stu-id="938f5-118">Description</span></span>|<span data-ttu-id="938f5-119">예</span><span class="sxs-lookup"><span data-stu-id="938f5-119">Example</span></span>|  
|------------------------|-----------------|-------------|  
|%|<span data-ttu-id="938f5-120">문자 0개 이상으로 이루어진 임의의 `string`입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-120">Any `string` of zero or more characters.</span></span>|<span data-ttu-id="938f5-121">`title like '%computer%'`단어 포함 된 모든 제목을 찾습니다 `"computer"` 는 제목에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-121">`title like '%computer%'` finds all titles with the word `"computer"` anywhere in the title.</span></span>|  
|<span data-ttu-id="938f5-122">_(밑줄)</span><span class="sxs-lookup"><span data-stu-id="938f5-122">_ (underscore)</span></span>|<span data-ttu-id="938f5-123">임의의 단일 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-123">Any single character.</span></span>|<span data-ttu-id="938f5-124">`firstname like '_ean'`은 Dean이나 Sean처럼 `"ean`"으로 끝나면서 4문자로 이루어진 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-124">`firstname like '_ean'` finds all four-letter first names that end with `"ean`," such as Dean or Sean.</span></span>|  
|<span data-ttu-id="938f5-125">[ ]</span><span class="sxs-lookup"><span data-stu-id="938f5-125">[ ]</span></span>|<span data-ttu-id="938f5-126">지정된 범위([a-f]) 또는 집합([abcdef]) 내의 임의의 단일 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-126">Any single character in the specified range ([a-f]) or set ([abcdef]).</span></span>|<span data-ttu-id="938f5-127">`lastname like '[C-P]arsen'`은 Carsen이나 Larsen처럼 C와 P 사이의 단일 문자로 시작되고 "arsen"으로 끝나는 성을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-127">`lastname like '[C-P]arsen'` finds last names ending with "arsen" and beginning with any single character between C and P, such as Carsen or Larsen.</span></span>|  
|<span data-ttu-id="938f5-128">[^]</span><span class="sxs-lookup"><span data-stu-id="938f5-128">[^]</span></span>|<span data-ttu-id="938f5-129">지정된 범위([^a-f]) 또는 집합([^abcdef])에 속하지 않는 임의의 단일 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-129">Any single character not in the specified range ([^a-f]) or set ([^abcdef]).</span></span>|<span data-ttu-id="938f5-130">`lastname like 'de[^l]%'`는 "de"로 시작되고 그 다음 문자에 "l"이 포함되지 않는 성을 모두 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-130">`lastname like 'de[^l]%'` finds all last names that begin with "de" and do not include "l" as the following letter.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="938f5-131">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] LIKE 연산자와 ESCAPE 절은 `System.DateTime` 또는 `System.Guid` 값에 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-131">The [!INCLUDE[esql](../../../../../../includes/esql-md.md)] LIKE operator and ESCAPE clause cannot be applied to `System.DateTime` or `System.Guid` values.</span></span>  
  
 <span data-ttu-id="938f5-132">LIKE는 ASCII 패턴 일치 및 유니코드 패턴 일치를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-132">LIKE supports ASCII pattern matching and Unicode pattern matching.</span></span> <span data-ttu-id="938f5-133">모든 매개 변수가 ASCII 문자인 경우 ASCII 패턴 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-133">When all parameters are ASCII characters, ASCII pattern matching is performed.</span></span> <span data-ttu-id="938f5-134">인수 하나 이상이 유니코드인 경우 모든 인수가 유니코드로 변환되고 유니코드 패턴 일치가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-134">If one or more of the arguments are Unicode, all arguments are converted to Unicode and Unicode pattern matching is performed.</span></span> <span data-ttu-id="938f5-135">LIKE로 유니코드를 사용할 경우에는 후행 공백이 중요하지만 비유니코드의 경우에는 후행 공백이 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-135">When you use Unicode with LIKE, trailing blanks are significant; however, for non-Unicode, trailing blanks are not significant.</span></span> <span data-ttu-id="938f5-136">[!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 패턴 문자열 구문은 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]의 구문과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-136">The pattern string syntax of [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is the same as that of [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="938f5-137">패턴에는 정규 문자와 와일드카드 문자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-137">A pattern can include regular characters and wildcard characters.</span></span> <span data-ttu-id="938f5-138">패턴 일치 과정에서 정규 문자는 문자 `string`에 지정된 문자와 정확히 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-138">During pattern matching, regular characters must exactly match the characters specified in the character `string`.</span></span> <span data-ttu-id="938f5-139">와일드카드 문자는 문자열의 임의의 부분과 일치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-139">However, wildcard characters can be matched with arbitrary fragments of the character string.</span></span> <span data-ttu-id="938f5-140">와일드카드 문자와 함께 사용할 때 LIKE 연산자는 = 및 != 문자열 비교 연산자보다 융통성이 뛰어납니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-140">When it is used with wildcard characters, the LIKE operator is more flexible than the = and != string comparison operators.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="938f5-141">특정 공급자를 대상으로 하는 경우 공급자 특정 확장을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-141">You may use provider-specific extensions if you target a specific provider.</span></span> <span data-ttu-id="938f5-142">하지만 그렇게 하면 다른 공급자에서 다르게 취급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-142">However, such constructs may be treated differently by other providers, for example.</span></span> <span data-ttu-id="938f5-143">SqlServer에서는 [first-last] 및 [^first-last] 패턴이 지원되며, 여기서 첫 번째는 first와 last 사이의 한 문자와 정확히 일치하고 두 번째는 first와 last 사이에 존재하지 않는 한 문자와 정확히 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-143">SqlServer supports [first-last] and [^first-last] patterns where the former matches exactly one character between first and last, and the latter matches exactly one character that is not between first and last.</span></span>  
  
### <a name="escape"></a><span data-ttu-id="938f5-144">이스케이프</span><span class="sxs-lookup"><span data-stu-id="938f5-144">Escape</span></span>  
 <span data-ttu-id="938f5-145">ESCAPE 절을 사용하면 이전 단원의 표에서 설명한 특수 와일드카드 문자가 한 개 이상 포함된 문자열을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-145">By using the ESCAPE clause, you can search for character strings that include one or more of the special wildcard characters described in the table in the previous section.</span></span> <span data-ttu-id="938f5-146">예를 들어, 여러 문서의 제목에 "100%"라는 리터럴이 포함되어 있고 해당 문서 전체에서 검색하려는 경우를 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-146">For example, assume several documents include the literal "100%" in the title and you want to search for all of those documents.</span></span> <span data-ttu-id="938f5-147">백분율(%) 문자는 와일드카드 문자이므로, 검색을 성공적으로 실행하려면 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ESCAPE 절을 사용하여 이 문자를 이스케이프 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-147">Because the percent (%) character is a wildcard character, you must escape it using the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ESCAPE clause to successfully execute the search.</span></span> <span data-ttu-id="938f5-148">다음은 이러한 필터의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-148">The following is an example of this filter.</span></span>  
  
```  
"title like '%100!%%' escape '!'"  
```  
  
 <span data-ttu-id="938f5-149">이 검색 식에서 느낌표(!) 문자 바로 다음에 나오는 백분율(%) 와일드카드 문자는 와일드카드 문자가 아니라 리터럴로 취급됩니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-149">In this search expression, the percent wildcard character (%) immediately following the exclamation point character (!) is treated as a literal, instead of as a wildcard character.</span></span> <span data-ttu-id="938f5-150">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 와일드카드 문자 및 대괄호(`[ ]`) 문자를 제외한 모든 문자를 이스케이프 문자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-150">You can use any character as an escape character except for the [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wildcard characters and the square bracket (`[ ]`) characters.</span></span> <span data-ttu-id="938f5-151">이전의 예제에서 느낌표(!) 문자가 이스케이프 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-151">In the previous example, the exclamation point (!) character is the escape character.</span></span>  
  
## <a name="example"></a><span data-ttu-id="938f5-152">예</span><span class="sxs-lookup"><span data-stu-id="938f5-152">Example</span></span>  
 <span data-ttu-id="938f5-153">다음 두 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 LIKE 및 ESCAPE 연산자를 사용하여 특정 문자열이 지정된 패턴과 일치하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-153">The following two [!INCLUDE[esql](../../../../../../includes/esql-md.md)] queries use the LIKE and ESCAPE operators to determine whether a specific character string matches a specified pattern.</span></span> <span data-ttu-id="938f5-154">첫 번째 쿼리는 `Name`이라는 문자로 시작되는 `Down_`을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-154">The first query searches for the `Name` that starts with the characters `Down_`.</span></span> <span data-ttu-id="938f5-155">이 쿼리에서는 밑줄(`_`)이 와일드카드 문자이므로 ESCAPE 옵션이 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-155">This query uses the ESCAPE option because the underscore (`_`) is a wildcard character.</span></span> <span data-ttu-id="938f5-156">ESCAPE 옵션이 지정 하지 않고 쿼리 검색할 것 `Name` 단어로 시작 하는 값 `Down` 밑줄 문자를 제외한 모든 단일 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-156">Without specifying the ESCAPE option, the query would search for any `Name` values that start with the word `Down` followed by any single character other than the underscore character.</span></span> <span data-ttu-id="938f5-157">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-157">The queries are based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="938f5-158">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="938f5-158">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="938f5-159">절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-159">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="938f5-160">다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="938f5-160">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#LIKE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#like)]  
  
## <a name="see-also"></a><span data-ttu-id="938f5-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="938f5-161">See Also</span></span>  
 [<span data-ttu-id="938f5-162">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="938f5-162">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
