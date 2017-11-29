---
title: "숫자 시퀀스에서 최소값 찾기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 78203093-f242-4572-9b31-9495b10926aa
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c040b2a9a4c806d6e0f82ea2b22113b44df7d4c0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="find-the-minimum-value-in-a-numeric-sequence"></a><span data-ttu-id="7e9b2-102">숫자 시퀀스에서 최소값 찾기</span><span class="sxs-lookup"><span data-stu-id="7e9b2-102">Find the Minimum Value in a Numeric Sequence</span></span>
<span data-ttu-id="7e9b2-103"><xref:System.Linq.Enumerable.Min%2A> 연산자를 사용하여 숫자 값 시퀀스의 최소값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-103">Use the <xref:System.Linq.Enumerable.Min%2A> operator to return the minimum value from a sequence of numeric values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e9b2-104">예제</span><span class="sxs-lookup"><span data-stu-id="7e9b2-104">Example</span></span>  
 <span data-ttu-id="7e9b2-105">다음 예제에서는 제품의 최저 단가를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-105">The following example finds the lowest unit price of any product.</span></span>  
  
 <span data-ttu-id="7e9b2-106">이 쿼리를 Northwind 샘플 데이터베이스에 대해 실행하면 `2.5000`이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-106">If you run this query against the Northwind sample database, the output is: `2.5000`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#9](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#9)]
 [!code-vb[DLinqQueryExamples#9](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#9)]  
  
## <a name="example"></a><span data-ttu-id="7e9b2-107">예제</span><span class="sxs-lookup"><span data-stu-id="7e9b2-107">Example</span></span>  
 <span data-ttu-id="7e9b2-108">다음 예제에서는 주문의 최소 운송 금액을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-108">The following example finds the lowest freight amount for any order.</span></span>  
  
 <span data-ttu-id="7e9b2-109">이 쿼리를 Northwind 샘플 데이터베이스에 대해 실행하면 `0.0200`이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-109">If you run this query against the Northwind sample database, the output is: `0.0200`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#10](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#10)]
 [!code-vb[DLinqQueryExamples#10](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="7e9b2-110">예제</span><span class="sxs-lookup"><span data-stu-id="7e9b2-110">Example</span></span>  
 <span data-ttu-id="7e9b2-111">다음 예제에서는 Min을 사용하여 각 범주에서 최저 단가의 `Products`를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-111">The following example uses Min to find the `Products` that have the lowest unit price in each category.</span></span> <span data-ttu-id="7e9b2-112">출력은 범주별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-112">The output is arranged by category.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#11](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#11)]
 [!code-vb[DLinqQueryExamples#11](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#11)]  
  
 <span data-ttu-id="7e9b2-113">Northwind 샘플 데이터베이스에 대해 이전 쿼리를 실행할 경우 결과는 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9b2-113">If you run the previous query against the Northwind sample database, your results will resemble the following:</span></span>  
  
 `1`  
  
 `Guaraná Fantástica`  
  
 `2`  
  
 `Aniseed Syrup`  
  
 `3`  
  
 `Teatime Chocolate Biscuits`  
  
 `4`  
  
 `Geitost`  
  
 `5`  
  
 `Filo Mix`  
  
 `6`  
  
 `Tourtière`  
  
 `7`  
  
 `Longlife Tofu`  
  
 `8`  
  
 `Konbu`  
  
## <a name="see-also"></a><span data-ttu-id="7e9b2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e9b2-114">See Also</span></span>  
 [<span data-ttu-id="7e9b2-115">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="7e9b2-115">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="7e9b2-116">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="7e9b2-116">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
