---
title: "시퀀스의 요소 수 계산"
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
ms.assetid: ccbe5d54-c9eb-4b14-b0ab-f628483c5f99
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: f6d1403384b8725720abbe9a81f98cbbfdb9c6e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="count-the-number-of-elements-in-a-sequence"></a><span data-ttu-id="0a867-102">시퀀스의 요소 수 계산</span><span class="sxs-lookup"><span data-stu-id="0a867-102">Count the Number of Elements in a Sequence</span></span>
<span data-ttu-id="0a867-103"><xref:System.Linq.Enumerable.Count%2A> 연산자를 사용하여 시퀀스의 요소 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0a867-103">Use the <xref:System.Linq.Enumerable.Count%2A> operator to count the number of elements in a sequence.</span></span>  
  
 <span data-ttu-id="0a867-104">Northwind 샘플 데이터베이스에 대한 쿼리를 실행하여 `91`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a867-104">Running this query against the Northwind sample database produces an output of `91`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a867-105">예</span><span class="sxs-lookup"><span data-stu-id="0a867-105">Example</span></span>  
 <span data-ttu-id="0a867-106">다음 예제에서는 데이터베이스의 `Customers` 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0a867-106">The following example counts the number of `Customers` in the database.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#4)]
 [!code-vb[DLinqQueryExamples#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="0a867-107">예</span><span class="sxs-lookup"><span data-stu-id="0a867-107">Example</span></span>  
 <span data-ttu-id="0a867-108">다음 예제에서는 데이터베이스에서 중지되지 않은 제품의 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="0a867-108">The following example counts the number of products in the database that have not been discontinued.</span></span>  
  
 <span data-ttu-id="0a867-109">Northwind 샘플 데이터베이스에 대한 예제를 실행하여 `69`의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a867-109">Running this example against the Northwind sample database produces an output of `69`.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#5)]
 [!code-vb[DLinqQueryExamples#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="0a867-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a867-110">See Also</span></span>  
 [<span data-ttu-id="0a867-111">집계 쿼리</span><span class="sxs-lookup"><span data-stu-id="0a867-111">Aggregate Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 [<span data-ttu-id="0a867-112">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="0a867-112">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
