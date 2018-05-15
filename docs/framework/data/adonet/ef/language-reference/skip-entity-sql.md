---
title: SKIP(Entity SQL)
ms.date: 03/30/2017
ms.assetid: e2139412-8ea4-451b-8f10-91af18dfa3ec
ms.openlocfilehash: 3b63ca6ade93331b9d1c3ef3e8de15ed520864dc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="skip-entity-sql"></a><span data-ttu-id="92c19-102">SKIP(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="92c19-102">SKIP (Entity SQL)</span></span>
<span data-ttu-id="92c19-103">ORDER BY 절의 SKIP 하위 절을 사용하여 물리적 페이징을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-103">You can perform physical paging by using the SKIP sub-clause in the ORDER BY clause.</span></span> <span data-ttu-id="92c19-104">SKIP 절은 ORDER BY 절과 별도로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-104">SKIP cannot be used separately from the ORDER BY clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92c19-105">구문</span><span class="sxs-lookup"><span data-stu-id="92c19-105">Syntax</span></span>  
  
```  
[ SKIP n ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="92c19-106">인수</span><span class="sxs-lookup"><span data-stu-id="92c19-106">Arguments</span></span>  
 `n`  
 <span data-ttu-id="92c19-107">건너뛸 항목의 개수입니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-107">The number of items to skip.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92c19-108">설명</span><span class="sxs-lookup"><span data-stu-id="92c19-108">Remarks</span></span>  
 <span data-ttu-id="92c19-109">SKIP 식 하위 절이 ORDER BY 절에 있으면 결과는 정렬 지정에 따라 정렬되고 SKIP 식 바로 뒤에 있는 행에서 시작하는 행이 결과 집합에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-109">If a SKIP expression sub-clause is present in an ORDER BY clause, the results will be sorted according the sort specification and the result set will include rows starting from the next row immediately after the SKIP expression.</span></span> <span data-ttu-id="92c19-110">예를 들어, SKIP 5를 사용하면 처음 다섯 개의 행을 건너뛰고 여섯 번째 행부터 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-110">For example, SKIP 5 will skip the first five rows and return from the sixth row forward.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92c19-111">TOP 한정자와 SKIP 하위 절이 모두 같은 쿼리 식에 있는 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 유효하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-111">An [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query is invalid if both the TOP modifier and the SKIP sub-clause are present in the same query expression.</span></span> <span data-ttu-id="92c19-112">TOP 식을 변경하여 쿼리를 LIMIT 식에 다시 써야 합니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-112">The query should be rewritten by changing the TOP expression to the LIMIT expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92c19-113">[!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]에서 키가 아닌 열에 ORDER BY와 함께 SKIP을 사용하면 잘못된 결과가 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-113">In [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)], using SKIP with ORDER BY on non-key columns might return incorrect results.</span></span> <span data-ttu-id="92c19-114">키가 아닌 열에 중복 데이터가 있는 경우, 지정된 개수 이상의 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-114">More than the specified number of rows might be skipped if the non-key column has duplicate data in it.</span></span> <span data-ttu-id="92c19-115">이런 현상은 SKIP이 [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)]에 맞게 변환되는 방식 때문에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-115">This is due to how SKIP is translated for [!INCLUDE[ssVersion2000](../../../../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="92c19-116">예를 들어 다음 코드에서는 `E.NonKeyColumn` 에 중복 값이 있으면 5개가 넘는 행을 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-116">For example, in the following code more than five rows might be skipped if `E.NonKeyColumn` has duplicate values:</span></span>  
>   
>  `SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L`  
  
 <span data-ttu-id="92c19-117">[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 이 [예제의](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) 쿼리는 SKIP과 함께 ORDER BY 연산자를 사용하여 SELECT 문에서 반환되는 개체에 적용하는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="92c19-117">The  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query in [this](https://msdn.microsoft.com/library/bb738702\(v=vs.100\).aspx#_ESQL) example uses the ORDER BY operator with SKIP to specify the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92c19-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="92c19-118">See Also</span></span>  
 [<span data-ttu-id="92c19-119">ORDER BY</span><span class="sxs-lookup"><span data-stu-id="92c19-119">ORDER BY</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [<span data-ttu-id="92c19-120">방법: 쿼리를 통해 페이지 결과</span><span class="sxs-lookup"><span data-stu-id="92c19-120">How to: Page Through Query Results</span></span>](http://msdn.microsoft.com/library/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [<span data-ttu-id="92c19-121">페이징</span><span class="sxs-lookup"><span data-stu-id="92c19-121">Paging</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [<span data-ttu-id="92c19-122">TOP</span><span class="sxs-lookup"><span data-stu-id="92c19-122">TOP</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
