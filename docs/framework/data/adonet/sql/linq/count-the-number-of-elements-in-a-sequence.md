---
title: 시퀀스의 요소 수 계산
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
ms.openlocfilehash: 928cfd33a187637c6d18da3cccefb22bb2950acf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353838"
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="9c075-102">시퀀스의 요소 수 계산</span><span class="sxs-lookup"><span data-stu-id="9c075-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="9c075-103"><xref:System.Linq.Enumerable.Count%2A> 연산자를 사용하여 시퀀스의 요소 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="9c075-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="9c075-104">Northwind 샘플 데이터베이스에 대한 쿼리를 실행하여 `91`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c075-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c075-105">예제</span><span class="sxs-lookup"><span data-stu-id="9c075-105">Example</span></span>  
 <span data-ttu-id="9c075-106">다음 예제에서는 데이터베이스의 `Customers` 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="9c075-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="9c075-107">예제</span><span class="sxs-lookup"><span data-stu-id="9c075-107">Example</span></span>  
 <span data-ttu-id="9c075-108">다음 예제에서는 데이터베이스에서 중지되지 않은 제품의 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="9c075-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="9c075-109">Northwind 샘플 데이터베이스에 대한 예제를 실행하여 `69`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9c075-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="9c075-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9c075-110">See Also</span></span>  
 [<span data-ttu-id="9c075-111">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="9c075-111">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="9c075-112">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="9c075-112">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
