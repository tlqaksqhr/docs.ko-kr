---
title: 시퀀스의 첫 번째 요소 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccdc3777-b2c2-44e3-a627-abef8d79a555
ms.openlocfilehash: fd228b2d7534feca3cff49586ac0d43fbf9bcb1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361350"
---
# <a name="return-the-first-element-in-a-sequence"></a><span data-ttu-id="6857a-102">시퀀스의 첫 번째 요소 반환</span><span class="sxs-lookup"><span data-stu-id="6857a-102">Return the First Element in a Sequence</span></span>
<span data-ttu-id="6857a-103"><xref:System.Linq.Enumerable.First%2A> 연산자를 사용하여 시퀀스의 첫 번째 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6857a-103">Use the <xref:System.Linq.Enumerable.First%2A> operator to return the first element in a sequence.</span></span> <span data-ttu-id="6857a-104"><xref:System.Linq.Enumerable.First%2A>를 사용한 쿼리는 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6857a-104">Queries that use <xref:System.Linq.Enumerable.First%2A> are executed immediately.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6857a-105">에서는 <xref:System.Linq.Enumerable.Last%2A> 연산자를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6857a-105"> does not support the <xref:System.Linq.Enumerable.Last%2A> operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6857a-106">예제</span><span class="sxs-lookup"><span data-stu-id="6857a-106">Example</span></span>  
 <span data-ttu-id="6857a-107">다음 코드에서는 테이블에서 첫 번째 `Shipper`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6857a-107">The following code finds the first `Shipper` in a table:</span></span>  
  
 <span data-ttu-id="6857a-108">Northwind 샘플 데이터베이스에 대한 쿼리를 실행하면 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6857a-108">If you run this query against the Northwind sample database, the results are</span></span>  
  
 <span data-ttu-id="6857a-109">`ID = 1, Company = Speedy Express`.</span><span class="sxs-lookup"><span data-stu-id="6857a-109">`ID = 1, Company = Speedy Express`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#14](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#14)]
 [!code-vb[DLinqQueryExamples#14](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="6857a-110">예제</span><span class="sxs-lookup"><span data-stu-id="6857a-110">Example</span></span>  
 <span data-ttu-id="6857a-111">다음 코드에서는 `Customer` BONAP이 있는 단일 `CustomerID`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="6857a-111">The following code finds the single `Customer` that has the `CustomerID` BONAP.</span></span>  
  
 <span data-ttu-id="6857a-112">Northwind 샘플 데이터베이스에 대해 이 쿼리를 실행하면 결과는 `ID = BONAP, Contact = Laurence Lebihan`입니다.</span><span class="sxs-lookup"><span data-stu-id="6857a-112">If you run this query against the Northwind sample database, the results are `ID = BONAP, Contact = Laurence Lebihan`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#15](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#15)]
 [!code-vb[DLinqQueryExamples#15](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#15)]  
  
## <a name="see-also"></a><span data-ttu-id="6857a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6857a-113">See Also</span></span>  
 [<span data-ttu-id="6857a-114">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="6857a-114">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 [<span data-ttu-id="6857a-115">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="6857a-115">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
