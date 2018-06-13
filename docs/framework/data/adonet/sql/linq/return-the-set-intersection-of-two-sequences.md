---
title: 두 시퀀스의 교집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 9fd2a5dc435829d08594ea3c2f1c129328386250
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358786"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="5451c-102">두 시퀀스의 교집합 반환</span><span class="sxs-lookup"><span data-stu-id="5451c-102">Return the Set Intersection of Two Sequences</span></span>
<span data-ttu-id="5451c-103"><xref:System.Linq.Queryable.Intersect%2A> 연산자를 사용하여 두 시퀀스의 교집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5451c-104">예제</span><span class="sxs-lookup"><span data-stu-id="5451c-104">Example</span></span>  
 <span data-ttu-id="5451c-105">이 예제에서는 <xref:System.Linq.Queryable.Intersect%2A>를 사용하여 `Customers`와 `Employees`가 모두 살고 있는 모든 국가의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="5451c-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Intersect%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="5451c-107">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5451c-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5451c-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5451c-108">See Also</span></span>  
 [<span data-ttu-id="5451c-109">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="5451c-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="5451c-110">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="5451c-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
