---
title: "방법: 테이블 반환 사용자 정의 함수 사용"
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
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c8ec97e0d083ccdd17a97db571d58aae9afbeea8
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="0ebcf-102">방법: 테이블 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="0ebcf-102">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="0ebcf-103">테이블 반환 함수에서는 여러 결과 모양을 반환할 수 있는 저장 프로시저와 달리 단일 행 집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-103">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="0ebcf-104">테이블 반환 함수의 반환 형식은 `Table`이기 때문에 테이블을 사용할 수 있는 SQL의 위치인 어디에나 테이블 반환 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-104">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="0ebcf-105">또한 테이블 반환 함수를 테이블로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-105">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ebcf-106">예</span><span class="sxs-lookup"><span data-stu-id="0ebcf-106">Example</span></span>  
 <span data-ttu-id="0ebcf-107">다음 SQL 함수는 `TABLE`을 반환한다는 것을 명시적으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-107">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="0ebcf-108">따라서 반환된 행 집합 구조는 암시적으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-108">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="0ebcf-109">에서는 함수를 다음과 같이 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-109"> maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="0ebcf-110">예</span><span class="sxs-lookup"><span data-stu-id="0ebcf-110">Example</span></span>  
 <span data-ttu-id="0ebcf-111">다음 SQL 코드에서는 함수에서 반환하는 테이블에 조인하거나 테이블 반환 함수를 원하는 다른 테이블로 처리할 수 있음을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-111">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="0ebcf-112">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 쿼리는 다음과 같이 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ebcf-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0ebcf-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ebcf-113">See Also</span></span>  
 [<span data-ttu-id="0ebcf-114">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="0ebcf-114">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
