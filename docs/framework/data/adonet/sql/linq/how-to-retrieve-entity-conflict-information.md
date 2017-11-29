---
title: "방법: 엔터티 충돌 정보 검색"
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
ms.assetid: 9a02b608-e7bb-4041-a452-a7fed26fd008
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 26f3ec3736b04eeffc1cd741e2c06a39ef7f1a0d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-entity-conflict-information"></a><span data-ttu-id="496f3-102">방법: 엔터티 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="496f3-102">How to: Retrieve Entity Conflict Information</span></span>
<span data-ttu-id="496f3-103"><xref:System.Data.Linq.ObjectChangeConflict> 클래스의 개체를 사용하여 <xref:System.Data.Linq.ChangeConflictException> 예외로 인해 발생한 충돌에 대한 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="496f3-103">You can use objects of the <xref:System.Data.Linq.ObjectChangeConflict> class to provide information about conflicts revealed by <xref:System.Data.Linq.ChangeConflictException> exceptions.</span></span> <span data-ttu-id="496f3-104">자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="496f3-104">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="496f3-105">예제</span><span class="sxs-lookup"><span data-stu-id="496f3-105">Example</span></span>  
 <span data-ttu-id="496f3-106">다음 예제에서는 누적된 충돌 목록을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="496f3-106">The following example iterates through a list of accumulated conflicts.</span></span>  
  
 [!code-csharp[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.objectchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ObjectChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.objectchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="496f3-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="496f3-107">See Also</span></span>  
 [<span data-ttu-id="496f3-108">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="496f3-108">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
