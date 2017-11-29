---
title: "방법: 트랜잭션을 사용하여 데이터 대괄호 전송"
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
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 071c0c8bc7e0bb8dca01e9fc51c66fb930ed102b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a><span data-ttu-id="7ecb0-102">방법: 트랜잭션을 사용하여 데이터 대괄호 전송</span><span class="sxs-lookup"><span data-stu-id="7ecb0-102">How to: Bracket Data Submissions by Using Transactions</span></span>
<span data-ttu-id="7ecb0-103"><xref:System.Transactions.TransactionScope>를 사용하여 데이터베이스에 대한 전송을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7ecb0-103">You can use <xref:System.Transactions.TransactionScope> to bracket your submissions to the database.</span></span> <span data-ttu-id="7ecb0-104">자세한 내용은 참조 [트랜잭션 지원](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7ecb0-104">For more information, see [Transaction Support](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ecb0-105">예제</span><span class="sxs-lookup"><span data-stu-id="7ecb0-105">Example</span></span>  
 <span data-ttu-id="7ecb0-106">다음 코드에서는 데이터베이스 전송을 <xref:System.Transactions.TransactionScope>로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="7ecb0-106">The following code encloses the database submission in a <xref:System.Transactions.TransactionScope>.</span></span>  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7ecb0-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ecb0-107">See Also</span></span>  
 [<span data-ttu-id="7ecb0-108">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="7ecb0-108">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="7ecb0-109">만들고 데이터 변경 내용을 전송</span><span class="sxs-lookup"><span data-stu-id="7ecb0-109">Making and Submitting Data Changes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)  
 [<span data-ttu-id="7ecb0-110">트랜잭션 지원</span><span class="sxs-lookup"><span data-stu-id="7ecb0-110">Transaction Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)
