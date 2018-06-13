---
title: '방법: 트랜잭션을 사용하여 데이터 대괄호 전송'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: aa77d364d1ee4efc09386dd7e889914aeb2f3f26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33361529"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="628bb-102">방법: 트랜잭션을 사용하여 데이터 대괄호 전송</span><span class="sxs-lookup"><span data-stu-id="628bb-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="628bb-103"><xref:System.Transactions.TransactionScope>를 사용하여 데이터베이스에 대한 전송을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="628bb-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="628bb-104">자세한 내용은 참조 [트랜잭션 지원](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="628bb-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="628bb-105">예제</span><span class="sxs-lookup"><span data-stu-id="628bb-105">Example</span></span>  
 <span data-ttu-id="628bb-106">다음 코드에서는 데이터베이스 전송을 <xref:System.Transactions.TransactionScope>로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="628bb-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="628bb-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="628bb-107">See Also</span></span>  
 [<span data-ttu-id="628bb-108">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="628bb-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="628bb-109">데이터 변경 및 변경 내용 전송</span><span class="sxs-lookup"><span data-stu-id="628bb-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="628bb-110">트랜잭션 지원</span><span class="sxs-lookup"><span data-stu-id="628bb-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
