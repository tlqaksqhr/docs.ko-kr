---
title: "방법: 변경 집합 표시"
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
ms.assetid: 126e7245-c5a0-4ebf-800d-cc1fcf9cd0ab
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7dd730e2337cdd735530107abaedd13b726e5cfc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-display-a-changeset"></a><span data-ttu-id="1d63e-102">방법: 변경 집합 표시</span><span class="sxs-lookup"><span data-stu-id="1d63e-102">How to: Display a ChangeSet</span></span>
<span data-ttu-id="1d63e-103"><xref:System.Data.Linq.DataContext>을 사용하여 <xref:System.Data.Linq.DataContext.GetChangeSet%2A>에 의해 추적된 변경 내용을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d63e-103">You can view changes tracked by a <xref:System.Data.Linq.DataContext> by using <xref:System.Data.Linq.DataContext.GetChangeSet%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d63e-104">예</span><span class="sxs-lookup"><span data-stu-id="1d63e-104">Example</span></span>  
 <span data-ttu-id="1d63e-105">다음 예제에서는 도시가 London인 고객을 검색하여 도시를 Paris로 변경한 다음 변경 내용을 다시 데이터베이스로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="1d63e-105">The following example retrieves customers whose city is London, changes the city to Paris, and submits the changes back to the database.</span></span>  
  
 [!code-csharp[DLinqDebuggingSupport#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#2)]
 [!code-vb[DLinqDebuggingSupport#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#2)]  
  
 <span data-ttu-id="1d63e-106">이 코드는 다음과 유사하게 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d63e-106">Output from this code appears similar to the following.</span></span> <span data-ttu-id="1d63e-107">맨 끝에 8개가 변경되었음을 요약하여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d63e-107">Note that the summary at the end shows that eight changes were made.</span></span>  
  
 `CustomerID: AROUT`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: BSBEV`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: CONSH`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: EASTC`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: NORTS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: PARIS`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SEVES`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 `CustomerID: SPECD`  
  
 `Original value: London`  
  
 `Updated value: Paris`  
  
 ``  
  
 `Total changes: {Added: 0, Removed: 0, Modified: 8}`  
  
## <a name="see-also"></a><span data-ttu-id="1d63e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d63e-108">See Also</span></span>  
 [<span data-ttu-id="1d63e-109">디버깅 지원</span><span class="sxs-lookup"><span data-stu-id="1d63e-109">Debugging Support</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
