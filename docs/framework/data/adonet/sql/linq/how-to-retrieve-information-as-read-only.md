---
title: "방법: 읽기 전용으로 정보 검색"
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
ms.assetid: fb09e298-0b53-47e5-97fb-ab318bcd4fad
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 9a9765d8d8330c7ad2a6e8cb25166427cdd9414a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-information-as-read-only"></a><span data-ttu-id="68d06-102">방법: 읽기 전용으로 정보 검색</span><span class="sxs-lookup"><span data-stu-id="68d06-102">How to: Retrieve Information As Read-Only</span></span>
<span data-ttu-id="68d06-103">데이터를 변경하지 않으려면 읽기 전용 결과를 검색하여 쿼리의 성능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68d06-103">When you do not intend to change the data, you can increase the performance of queries by seeking read-only results.</span></span>  
  
 <span data-ttu-id="68d06-104"><xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 `false`로 설정하여 읽기 전용 처리를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="68d06-104">You implement read-only processing by setting <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68d06-105"><xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A>를 `false`로 설정한 경우 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>는 암시적으로 `false`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="68d06-105">When <xref:System.Data.Linq.DataContext.ObjectTrackingEnabled%2A> is set to `false`, <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A> is implicitly set to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68d06-106">예제</span><span class="sxs-lookup"><span data-stu-id="68d06-106">Example</span></span>  
 <span data-ttu-id="68d06-107">다음 코드에서는 직원 고용 날짜의 읽기 전용 컬렉션을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="68d06-107">The following code retrieves a read-only collection of employee hire dates.</span></span>  
  
 [!code-csharp[DLinqQuerying#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#2)]
 [!code-vb[DLinqQuerying#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="68d06-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68d06-108">See Also</span></span>  
 [<span data-ttu-id="68d06-109">쿼리 개념</span><span class="sxs-lookup"><span data-stu-id="68d06-109">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="68d06-110">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="68d06-110">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)  
 [<span data-ttu-id="68d06-111">지연 된 실행과 즉시 로드 비교</span><span class="sxs-lookup"><span data-stu-id="68d06-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)
