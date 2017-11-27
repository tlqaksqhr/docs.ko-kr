---
title: "방법: 스칼라 반환 사용자 정의 함수 사용"
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
ms.assetid: 714e252f-c053-4bbb-b1f3-924111cd4d97
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: ef9e687522e200487e0fc2a661bbd545d4eb4bbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-scalar-valued-user-defined-functions"></a><span data-ttu-id="bef97-102">방법: 스칼라 반환 사용자 정의 함수 사용</span><span class="sxs-lookup"><span data-stu-id="bef97-102">How to: Use Scalar-Valued User-Defined Functions</span></span>
<span data-ttu-id="bef97-103"><xref:System.Data.Linq.Mapping.FunctionAttribute> 특성을 사용하여 클래스에 정의된 클라이언트 메서드를 사용자 정의 함수에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef97-103">You can map a client method defined on a class to a user-defined function by using the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute.</span></span> <span data-ttu-id="bef97-104">메서드 본문에서는 메서드 호출 목적을 캡처하는 식을 생성하여 해당 식을 변환 및 실행을 위해 <xref:System.Data.Linq.DataContext>로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bef97-104">Note that the body of the method constructs an expression that captures the intent of the method call, and passes that expression to the <xref:System.Data.Linq.DataContext> for translation and execution.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bef97-105">함수를 쿼리 외부에서 호출한 경우에만 직접 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bef97-105">Direct execution occurs only if the function is called outside a query.</span></span> <span data-ttu-id="bef97-106">자세한 내용은 참조 [하는 방법: Call User-Defined 함수를 인라인으로](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bef97-106">For more information, see [How to: Call User-Defined Functions Inline](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bef97-107">예제</span><span class="sxs-lookup"><span data-stu-id="bef97-107">Example</span></span>  
 <span data-ttu-id="bef97-108">다음 SQL 코드에서는 스칼라 반환 사용자 정의 함수인 `ReverseCustName()`을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bef97-108">The following SQL code presents a scalar-valued user-defined function `ReverseCustName()`.</span></span>  
  
```  
CREATE FUNCTION ReverseCustName(@string varchar(100))  
RETURNS varchar(100)  
AS  
BEGIN  
    DECLARE @custName varchar(100)  
    -- Implementation left as exercise for users.  
    RETURN @custName  
END  
```  
  
 <span data-ttu-id="bef97-109">사용자는 이 코드에 대해 다음과 같은 클라이언트 메서드를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bef97-109">You would map a client method such as the following for this code:</span></span>  
  
 [!code-csharp[DLinqUDFS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#3)]
 [!code-vb[DLinqUDFS#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="bef97-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bef97-110">See Also</span></span>  
 [<span data-ttu-id="bef97-111">사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="bef97-111">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
