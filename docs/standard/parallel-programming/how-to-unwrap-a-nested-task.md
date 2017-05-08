---
title: "How to: Unwrap a Nested Task | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "tasks, how to unwrap nested tasks"
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unwrap a Nested Task
다음 예제와 같이 메서드에서 작업을 반환한 후 해당 작업을 대기하거나 계속할 수 있습니다.  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 앞의 예제에서 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성은 `string`\(Visual Basic에서는 `String`\) 형식입니다.  
  
 그러나 일부 시나리오에서는 다른 작업 내에서 작업을 만든 다음 중첩 작업을 반환해야 할 수도 있습니다.  이 경우에는 다른 작업을 포함하는 작업의 `TResult` 자체가 하나의 작업입니다.  다음 예제에서 Result 속성은 C\#의 `Task<Task<string>>`이거나 Visual Basic의 `Task(Of Task(Of String))`입니다.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 외부 작업의 래핑을 취소하고 원래 작업 및 <xref:System.Threading.Tasks.Task%601.Result%2A> 속성을 검색하는 코드를 작성할 수 있지만 이 경우 예외 및 취소 요청을 처리해야 하기 때문에 코드 작성이 쉽지는 않습니다.  이 상황에서는 다음 예제와 같이 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 확장 메서드 중 하나를 사용하는 것이 좋습니다.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 메서드는 `Task<Task>` 또는 `Task<Task<TResult>>`\(Visual Basic의 경우 `Task(Of Task)` or `Task(Of Task(Of TResult))`\)를 `Task` or `Task<TResult>` \(Visual Basic의 경우 `Task(Of TResult)`\)로 변환하는 데 사용할 수 있습니다.  새 작업은 내부 중첩 작업을 완전히 나타내고, 취소 상태 및 모든 예외를 포함합니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> 예외 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## 참고 항목  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=fullName>   
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)