---
title: '방법: SQL 명령 직접 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
ms.openlocfilehash: 90fb0d7027946ce4f38c2ba4930ac3510e2a42b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33351874"
---
# <a name="how-to-directly-execute-sql-commands"></a><span data-ttu-id="08ad6-102">방법: SQL 명령 직접 실행</span><span class="sxs-lookup"><span data-stu-id="08ad6-102">How to: Directly Execute SQL Commands</span></span>
<span data-ttu-id="08ad6-103"><xref:System.Data.Linq.DataContext> 연결에서는 <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 개체를 반환하지 않는 SQL 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08ad6-103">Assuming a <xref:System.Data.Linq.DataContext> connection, you can use <xref:System.Data.Linq.DataContext.ExecuteCommand%2A> to execute SQL commands that do not return objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="08ad6-104">예제</span><span class="sxs-lookup"><span data-stu-id="08ad6-104">Example</span></span>  
 <span data-ttu-id="08ad6-105">다음 예제에서는 SQL 서버에서 UnitPrice를 1.00만큼 증가시키는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08ad6-105">The following example causes SQL Server to increase UnitPrice by 1.00.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="08ad6-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08ad6-106">See Also</span></span>  
 [<span data-ttu-id="08ad6-107">방법: SQL 쿼리 직접 실행</span><span class="sxs-lookup"><span data-stu-id="08ad6-107">How to: Directly Execute SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [<span data-ttu-id="08ad6-108">데이터베이스와 통신</span><span class="sxs-lookup"><span data-stu-id="08ad6-108">Communicating with the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
