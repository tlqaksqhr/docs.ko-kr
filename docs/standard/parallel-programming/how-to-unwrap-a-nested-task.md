---
title: "방법: 중첩된 작업 래핑 취소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a>방법: 중첩된 작업 래핑 취소
있습니다 수는 메서드에서 작업을 반환 하 고 대기 하거나 다음 예제와 같이 해당 작업을 계속:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 이전 예에서 <xref:System.Threading.Tasks.Task%601.Result%2A> 형식의 속성은 `string` (`String` Visual basic에서).  
  
 하지만, 일부 시나리오에서는 다른 작업 내에서 작업을 만든 다음 중첩된 된 작업을 반환 하 필요할 수 있습니다. 이 경우에 `TResult` 포함 하는 작업의 자체가 하나의 작업입니다. 다음 예제에서는 결과 속성은 한 `Task<Task<string>>` C# 또는 `Task(Of Task(Of String))` Visual Basic의 합니다.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 외부 작업 래핑 취소 하 고 원래 작업을 검색 하도록 코드를 작성할 수 있지만 및 해당 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성, 이러한 코드는 예외 및 취소 요청을 처리 해야 하기 때문에 쓸 하기 쉽지 않습니다. 이러한 경우 중 하나를 사용 하는 권장는 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 확장명 메서드를 다음 예제와 같이 합니다.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 메서드를 사용 하 여 모든 변환할 수 있습니다 `Task<Task>` 또는 `Task<Task<TResult>>` (`Task(Of Task)` 또는 `Task(Of Task(Of TResult))` Visual basic에서)에 `Task` 또는 `Task<TResult>` (`Task(Of TResult)` Visual basic에서). 새 작업 내부 중첩 된 작업을 완벽 하 게 나타내며 취소 상태 및 모든 예외를 포함 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 확장 메서드입니다.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [작업 기반 비동기 프로그래밍](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
