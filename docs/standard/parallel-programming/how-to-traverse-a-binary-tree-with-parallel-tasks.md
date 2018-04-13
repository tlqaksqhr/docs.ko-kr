---
title: '방법: 병렬 작업을 사용하여 이진 트리 트래버스'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 0196d82dd46a105f7cf1db0f9333a5d28afe559b
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="05dcb-102">방법: 병렬 작업을 사용하여 이진 트리 트래버스</span><span class="sxs-lookup"><span data-stu-id="05dcb-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="05dcb-103">다음 예제는 병렬 작업을 사용하여 트리 데이터 구조를 트래버스할 수 있는 두 가지 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="05dcb-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="05dcb-104">트리 자체의 생성은 실행으로 남습니다.</span><span class="sxs-lookup"><span data-stu-id="05dcb-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05dcb-105">예</span><span class="sxs-lookup"><span data-stu-id="05dcb-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="05dcb-106">표시된 두 가지 방법은 기능적으로 동등합니다.</span><span class="sxs-lookup"><span data-stu-id="05dcb-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="05dcb-107"><xref:System.Threading.Tasks.TaskFactory.StartNew%2A> 메서드를 사용하여 작업을 생성하고 실행함으로써 작업을 대기하고 예외를 처리하는 데 사용할 수 있는 작업에서 핸들을 다시 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05dcb-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05dcb-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05dcb-108">See Also</span></span>  
 [<span data-ttu-id="05dcb-109">TPL(작업 병렬 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="05dcb-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
