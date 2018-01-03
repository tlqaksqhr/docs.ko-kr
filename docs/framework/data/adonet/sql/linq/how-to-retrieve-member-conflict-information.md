---
title: "방법: 멤버 충돌 정보 검색"
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
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: e9dd92ad1b5c91798923296def8f207637b4bad2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-member-conflict-information"></a><span data-ttu-id="5756b-102">방법: 멤버 충돌 정보 검색</span><span class="sxs-lookup"><span data-stu-id="5756b-102">How to: Retrieve Member Conflict Information</span></span>
<span data-ttu-id="5756b-103"><xref:System.Data.Linq.MemberChangeConflict> 클래스를 사용하여 충돌의 각 멤버에 대한 정보를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5756b-103">You can use the <xref:System.Data.Linq.MemberChangeConflict> class to retrieve information about individual members in conflict.</span></span> <span data-ttu-id="5756b-104">이와 동일한 컨텍스트에서 멤버의 충돌에 대한 사용자 지정 처리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5756b-104">In this same context you can provide for custom handling of the conflict for any member.</span></span> <span data-ttu-id="5756b-105">자세한 내용은 참조 [낙관적 동시성: 개요](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5756b-105">For more information, see [Optimistic Concurrency: Overview](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5756b-106">예</span><span class="sxs-lookup"><span data-stu-id="5756b-106">Example</span></span>  
 <span data-ttu-id="5756b-107">다음 코드에서는 <xref:System.Data.Linq.ObjectChangeConflict> 개체를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5756b-107">The following code iterates through the <xref:System.Data.Linq.ObjectChangeConflict> objects.</span></span> <span data-ttu-id="5756b-108">그런 다음 각 개체에 대해 <xref:System.Data.Linq.MemberChangeConflict> 개체를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="5756b-108">For each object, it then iterates through the <xref:System.Data.Linq.MemberChangeConflict> objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5756b-109"><xref:System.Reflection> 정보를 제공하려면 <xref:System.Data.Linq.MemberChangeConflict.Member%2A>을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5756b-109">Include <xref:System.Reflection> in order to provide <xref:System.Data.Linq.MemberChangeConflict.Member%2A> information.</span></span>  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5756b-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5756b-110">See Also</span></span>  
 [<span data-ttu-id="5756b-111">방법: 변경 내용 충돌 관리</span><span class="sxs-lookup"><span data-stu-id="5756b-111">How to: Manage Change Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
