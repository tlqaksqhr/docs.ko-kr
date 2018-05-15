---
title: '- (나누기) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: ef48c368-f3ed-4275-8ada-4e9649781262
ms.openlocfilehash: 506553de78ce9fbdf5f3710805906ee8cd5b8757
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="-divide-entity-sql"></a><span data-ttu-id="64241-102">/ (나누기) (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="64241-102">/ (Divide) (Entity SQL)</span></span>
<span data-ttu-id="64241-103">한 숫자를 다른 숫자로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="64241-103">Divides one number by another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64241-104">구문</span><span class="sxs-lookup"><span data-stu-id="64241-104">Syntax</span></span>  
  
```  
dividend / divisor  
```  
  
## <a name="arguments"></a><span data-ttu-id="64241-105">인수</span><span class="sxs-lookup"><span data-stu-id="64241-105">Arguments</span></span>  
 `dividend`  
 <span data-ttu-id="64241-106">나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="64241-106">The numeric expression to divide.</span></span> <span data-ttu-id="64241-107">`dividend` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="64241-107">`dividend` is any valid expression of any one of the numeric data types.</span></span>  
  
 `divisor`  
 <span data-ttu-id="64241-108">피제수를 나눌 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="64241-108">The numeric expression to divide the dividend by.</span></span> <span data-ttu-id="64241-109">`divisor` 는 숫자 데이터 형식의 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="64241-109">`divisor` is any valid expression of any one of the numeric data types.</span></span>  
  
## <a name="result-types"></a><span data-ttu-id="64241-110">결과 형식</span><span class="sxs-lookup"><span data-stu-id="64241-110">Result Types</span></span>  
 <span data-ttu-id="64241-111">두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="64241-111">The data type that results from the implicit type promotion of the two arguments.</span></span> <span data-ttu-id="64241-112">암시적 형식 승격에 대 한 자세한 내용은 참조 [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64241-112">For more information about implicit type promotion, see [Type System](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="64241-113">예제</span><span class="sxs-lookup"><span data-stu-id="64241-113">Example</span></span>  
 <span data-ttu-id="64241-114">다음 Entity SQL 쿼리에서는 / 산술 연산자를 사용하여 한 숫자를 다른 숫자로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="64241-114">The following Entity SQL query uses the / arithmetic operator to divide one numer by another.</span></span> <span data-ttu-id="64241-115">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="64241-115">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="64241-116">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="64241-116">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="64241-117">[방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="64241-117">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="64241-118">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="64241-118">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#DIVIDE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#divide)]  
  
## <a name="see-also"></a><span data-ttu-id="64241-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64241-119">See Also</span></span>  
 [<span data-ttu-id="64241-120">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="64241-120">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
