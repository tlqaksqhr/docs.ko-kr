---
title: 두 시퀀스의 합집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b8bd3cb-86d4-4a3b-9906-61f68726dd1f
ms.openlocfilehash: 13e5e821f68e839039569b4ac8a993a20c45ab27
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37403949"
---
# <a name="return-the-set-union-of-two-sequences"></a><span data-ttu-id="6a3c6-102">두 시퀀스의 합집합 반환</span><span class="sxs-lookup"><span data-stu-id="6a3c6-102">Return the Set Union of Two Sequences</span></span>
<span data-ttu-id="6a3c6-103"><xref:System.Linq.Queryable.Union%2A> 연산자를 사용하여 두 시퀀스의 합집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-103">Use the <xref:System.Linq.Queryable.Union%2A> operator to return the set union of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a3c6-104">예</span><span class="sxs-lookup"><span data-stu-id="6a3c6-104">Example</span></span>  
 <span data-ttu-id="6a3c6-105">이 예제에서는 <xref:System.Linq.Queryable.Union%2A>을 사용하여 `Customers` 또는 `Employees`가 있는 모든 국가의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3c6-105">This example uses <xref:System.Linq.Queryable.Union%2A> to return a sequence of all countries in which there are either `Customers` or `Employees`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#43](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#43)]
 [!code-vb[DLinqQueryExamples#43](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#43)]  
  
 <span data-ttu-id="6a3c6-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]는 <xref:System.Linq.Queryable.Union%2A> 다중 집합의 순서가 지정 되지 않은 연결으로 다중 집합에 대해 연산자가 정의 (효율적인 결과 합니다 [ `UNION ALL` ](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) SQL 절).</span><span class="sxs-lookup"><span data-stu-id="6a3c6-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Union%2A> operator is defined for multisets as the unordered concatenation of the multisets (effectively the result of the [`UNION ALL`](https://docs.microsoft.com/en-us/sql/t-sql/language-elements/set-operators-union-transact-sql?view=sql-server-2017) clause in SQL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3c6-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a3c6-107">See Also</span></span>  
 [<span data-ttu-id="6a3c6-108">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="6a3c6-108">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="6a3c6-109">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="6a3c6-109">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
