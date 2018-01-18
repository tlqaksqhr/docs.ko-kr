---
title: "방법: 동시성 충돌 확인 지정"
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
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 51176e53af158536ab895c64a8eb3cf015aa01b1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="e7851-102">방법: 동시성 충돌 확인 지정</span><span class="sxs-lookup"><span data-stu-id="e7851-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="e7851-103"><xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출하는 경우 동시성 충돌을 검사할 데이터베이스의 열을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7851-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="e7851-104">자세한 내용은 참조 [하는 방법: 동시성 충돌에 대 한 지정 있는 멤버를 테스트](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e7851-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7851-105">예</span><span class="sxs-lookup"><span data-stu-id="e7851-105">Example</span></span>  
 <span data-ttu-id="e7851-106">다음 코드에서는 업데이트를 확인하는 동안 `HomePage` 멤버를 테스트하지 말아야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7851-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="e7851-107">자세한 내용은 <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7851-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e7851-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7851-108">See Also</span></span>  
 [<span data-ttu-id="e7851-109">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="e7851-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="e7851-110">방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="e7851-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
