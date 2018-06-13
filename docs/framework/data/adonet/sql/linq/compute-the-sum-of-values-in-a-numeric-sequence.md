---
title: 숫자 시퀀스에서 값의 합계 계산
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 24e335b0-984e-4825-8721-0a91b533b7c3
ms.openlocfilehash: d1c49d45eaf82101e57e0886af52a134d24b1651
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361431"
---
# <a name="compute-the-sum-of-values-in-a-numeric-sequence"></a><span data-ttu-id="3567d-102">숫자 시퀀스에서 값의 합계 계산</span><span class="sxs-lookup"><span data-stu-id="3567d-102">Compute the Sum of Values in a Numeric Sequence</span></span>
<span data-ttu-id="3567d-103"><xref:System.Linq.Enumerable.Sum%2A> 연산자를 사용하여 시퀀스의 숫자 값의 합을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-103">Use the <xref:System.Linq.Enumerable.Sum%2A> operator to compute the sum of numeric values in a sequence.</span></span>  
  
 <span data-ttu-id="3567d-104">`Sum`에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 연산자의 다음과 같은 특징에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="3567d-104">Note the following characteristics of the `Sum` operator in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
-   <span data-ttu-id="3567d-105">표준 쿼리 연산자의 집계 연산자인 `Sum`은 빈 시퀀스 또는 null만 들어 있는 시퀀스를 0으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-105">The Standard Query Operator aggregate operator `Sum` evaluates to zero for an empty sequence or a sequence that contains only nulls.</span></span> <span data-ttu-id="3567d-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 SQL 구문이 바뀌지 않고 남아 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the semantics of SQL are left unchanged.</span></span> <span data-ttu-id="3567d-107">따라서 `Sum`은 빈 시퀀스 또는 null만 들어 있는 시퀀스를 0이 아닌 null로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-107">For this reason, `Sum` evaluates to null instead of to zero for an empty sequence or for a sequence that contains only nulls.</span></span>  
  
-   <span data-ttu-id="3567d-108">중간 결과에 대한 SQL 제한은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 집계에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-108">SQL limitations on intermediate results apply to aggregates in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="3567d-109">32비트 정수 수량은 64비트 결과를 사용하여 계산되지 않으며 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 `Sum` 변환에 대해 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-109">Sum of 32-bit integer quantities is not computed by using 64-bit results, and overflow can occur for the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translation of `Sum`.</span></span> <span data-ttu-id="3567d-110">이러한 가능성은 표준 쿼리 연산자 구현이 메모리 내의 해당 시퀀스에 대해 오버플로를 발생시키지 않는 경우에도 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-110">This possibility exists even if the Standard Query Operator implementation does not cause an overflow for the corresponding in-memory sequence.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3567d-111">예제</span><span class="sxs-lookup"><span data-stu-id="3567d-111">Example</span></span>  
 <span data-ttu-id="3567d-112">다음 예제에서는 `Order` 테이블에서 모든 주문의 총 운송료를 검색합니다. </span><span class="sxs-lookup"><span data-stu-id="3567d-112">The following example finds the total freight of all orders in the `Order` table.</span></span>  
  
 <span data-ttu-id="3567d-113">이 쿼리를 Northwind 샘플 데이터베이스에 대해 실행하면 `64942.6900`이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-113">If you run this query against the Northwind sample database, the output is: `64942.6900`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#12](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#12)]
 [!code-vb[DLinqQueryExamples#12](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="3567d-114">예제</span><span class="sxs-lookup"><span data-stu-id="3567d-114">Example</span></span>  
 <span data-ttu-id="3567d-115">다음 예제에서는 모든 주문에 대한 총 단위 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-115">The following example finds the total number of units on order for all products.</span></span>  
  
 <span data-ttu-id="3567d-116">이 쿼리를 Northwind 샘플 데이터베이스에 대해 실행하면 `780`이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-116">If you run this query against the Northwind sample database, the output is: `780`.</span></span>  
  
 <span data-ttu-id="3567d-117">`short`에는 short 형식에 대한 오버로드가 없으므로 `UnitsOnOrder` 형식(예: `Sum`)을 캐스팅해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3567d-117">Note that you must cast `short` types (for example, `UnitsOnOrder`) because `Sum` has no overload for short types.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#13](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#13)]
 [!code-vb[DLinqQueryExamples#13](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="3567d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3567d-118">See Also</span></span>  
 [<span data-ttu-id="3567d-119">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="3567d-119">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="3567d-120">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="3567d-120">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
