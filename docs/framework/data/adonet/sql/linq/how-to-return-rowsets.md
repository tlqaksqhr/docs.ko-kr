---
title: '방법: 행 집합 반환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: a2666b752d936e10d377113d5bf18111393df3ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361139"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="aaf44-102">방법: 행 집합 반환</span><span class="sxs-lookup"><span data-stu-id="aaf44-102">How to: Return Rowsets</span></span>
<span data-ttu-id="aaf44-103">이 예제에서는 데이터베이스의 행 집합을 반환하고 입력 매개 변수를 사용하여 결과를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf44-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="aaf44-104">사용 하는 행 집합을 반환 하는 저장된 프로시저를 실행 해도 *결과* 저장된 프로시저의 반환을 저장 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="aaf44-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="aaf44-105">자세한 내용은 참조 [분석 LINQ to SQL 원본 코드](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf44-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaf44-106">예제</span><span class="sxs-lookup"><span data-stu-id="aaf44-106">Example</span></span>  
 <span data-ttu-id="aaf44-107">다음 예제에서는 고객의 행을 반환하고 입력 매개 변수를 사용하여 고객의 도시가 "London"인 행만을 반환하는 저장 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aaf44-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="aaf44-108">예제에서는 열거 가능한 `CustomersByCityResult` 클래스로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="aaf44-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="aaf44-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aaf44-109">See Also</span></span>  
 [<span data-ttu-id="aaf44-110">저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="aaf44-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [<span data-ttu-id="aaf44-111">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="aaf44-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
