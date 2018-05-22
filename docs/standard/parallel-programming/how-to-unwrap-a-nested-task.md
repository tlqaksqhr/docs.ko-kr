---
title: '방법: 중첩된 작업 래핑 취소'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f9cee6817378503a3b98424ff4166725a46f7a29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-unwrap-a-nested-task"></a><span data-ttu-id="0bdb5-102">방법: 중첩된 작업 래핑 취소</span><span class="sxs-lookup"><span data-stu-id="0bdb5-102">How to: Unwrap a Nested Task</span></span>
<span data-ttu-id="0bdb5-103">메서드에서 작업을 반환한 후 다음 예제와 같이 해당 작업을 대기하거나 계속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-103">You can return a task from a method, and then wait on or continue from that task, as shown in the following example:</span></span>  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 <span data-ttu-id="0bdb5-104">이전 예제에서 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성은 `string`(Visual Basic의 경우 `String`) 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-104">In the previous example, the <xref:System.Threading.Tasks.Task%601.Result%2A> property is of type `string` (`String` in Visual Basic).</span></span>  
  
 <span data-ttu-id="0bdb5-105">그러나 일부 시나리오에서는 다른 작업 내에 작업을 만들고 중첩된 작업을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-105">However, in some scenarios, you might want to create a task within another task, and then return the nested task.</span></span> <span data-ttu-id="0bdb5-106">이 경우 바깥쪽 작업의 `TResult` 자체가 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-106">In this case, the `TResult` of the enclosing task is itself a task.</span></span> <span data-ttu-id="0bdb5-107">다음 예제에서 Result 속성은 C#의 경우 `Task(Of Task(Of String))` 또는 Visual Basic의 경우 `Task<Task<string>>`입니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-107">In the following example, the Result property is a `Task<Task<string>>` in C# or `Task(Of Task(Of String))` in Visual Basic.</span></span>  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 <span data-ttu-id="0bdb5-108">외부 작업을 래핑 해제하고 원래 작업 및 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성을 검색하는 코드를 작성할 수 있지만, 예외 및 취소 요청을 처리해야 하므로 이러한 코드를 작성하기가 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-108">Although it is possible to write code to unwrap the outer task and retrieve the original task and its <xref:System.Threading.Tasks.Task%601.Result%2A> property, such code is not easy to write because you must handle exceptions and also cancellation requests.</span></span> <span data-ttu-id="0bdb5-109">이 경우 다음 예와 같이 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 확장 메서드 중 하나를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-109">In this situation, we recommend that you use one of the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <span data-ttu-id="0bdb5-110"><xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 메서드를 사용하면 `Task<Task>` 또는 `Task<Task<TResult>>`(Visual Basic의 경우 `Task(Of Task)` 또는 `Task(Of Task(Of TResult))`)를 `Task` 또는 `Task<TResult>`(Visual Basic의 경우 `Task(Of TResult)`)로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-110">The <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> methods can be used to transform any `Task<Task>` or `Task<Task<TResult>>` (`Task(Of Task)` or `Task(Of Task(Of TResult))` in Visual Basic) to a `Task` or `Task<TResult>` (`Task(Of TResult)` in Visual Basic).</span></span> <span data-ttu-id="0bdb5-111">새 작업은 내부 중첩 작업을 완전히 나타내며 취소 상태 및 모든 예외를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-111">The new task fully represents the inner nested task, and includes cancellation state and all exceptions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bdb5-112">예</span><span class="sxs-lookup"><span data-stu-id="0bdb5-112">Example</span></span>  
 <span data-ttu-id="0bdb5-113">다음 예제는 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 확장 메서드를 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bdb5-113">The following example demonstrates how to use the <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> extension methods.</span></span>  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a><span data-ttu-id="0bdb5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bdb5-114">See Also</span></span>  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [<span data-ttu-id="0bdb5-115">작업 기반 비동기 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="0bdb5-115">Task-based Asynchronous Programming</span></span>](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
