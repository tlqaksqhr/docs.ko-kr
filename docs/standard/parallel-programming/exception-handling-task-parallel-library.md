---
title: "예외 처리(작업 병렬 라이브러리)"
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
helpviewer_keywords: tasks, exceptions
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e62498376d321d8ff22a53315b9d5f18a8865056
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling-task-parallel-library"></a>예외 처리(작업 병렬 라이브러리)
작업 내에서 실행되는 사용자 코드에 의해 throw된 처리되지 않은 예외는 이 항목의 뒷부분에서 설명하는 특정 시나리오를 제외하고는 호출 스레드로 다시 전파됩니다. 정적 중 하나를 사용 하는 경우 예외는 전파 또는 인스턴스 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> 또는 <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` 메서드를 처리 하려면 해당 호출에 `try` / `catch` 문. 어떤 작업이 연결된 자식 작업의 부모인 경우 또는 여러 작업에서 대기 중인 경우, 여러 개의 예외가 throw될 수 있습니다.  
  
 모든 예외를 호출 스레드로 다시 전파하기 위해 작업 인프라가 이러한 예외를 <xref:System.AggregateException> 인스턴스에서 래핑합니다. <xref:System.AggregateException> 예외에는 <xref:System.AggregateException.InnerExceptions%2A> 속성이 있으며 이 속성을 열거하면 throw된 모든 원래 예외를 확인하고 각 예외를 개별적으로 처리하거나 처리하지 않을 수 있습니다. 사용 하 여 원래 예외를 처리할 수도 있습니다는 <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> 메서드.  
  
 하나의 예외만 throw된 경우 다음 예제와 같이 <xref:System.AggregateException> 예외에서 여전히 래핑됩니다.  
  
 [!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
 [!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]  
  
 <xref:System.AggregateException> 을 catch하고 내부 예외를 관찰하지 않으면 처리되지 않은 예외를 방지할 수 있습니다. 하지만 이 방법은 기본 <xref:System.Exception> 유형을 비병렬 시나리오에서 catch하는 것과 유사하기 때문에 사용하지 않는 것이 좋습니다. 복구하기 위한 특정 작업을 수행하지 않고 예외를 catch하려면 프로그램을 결정할 수 없는 상태 그대로 두면 됩니다.  
  
 호출 하지 않을 경우는 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> 또는 <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` 작업의 완료를 기다리는 메서드를 검색할 수도 있습니다는 <xref:System.AggregateException> 작업의 예외 <xref:System.Threading.Tasks.Task.Exception%2A> 다음 예제와 같이 속성입니다. 자세한 내용은 이 항목의 [Task.Exception 속성을 사용하여 예외 관찰](#ExceptionProp) 섹션을 참조하세요.  
  
 [!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
 [!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]  
  
 예외를 전파하는 작업을 기다리지 않거나 해당 <xref:System.Threading.Tasks.Task.Exception%2A> 속성에 액세스하는 경우 작업이 가비지 수집될 때 .NET 예외 정책에 따라 예외가 에스컬레이션됩니다.  
  
 예외가 가입된 스레드로 다시 버블 업될 수 있는 경우 예외가 발생한 후에도 작업에서 일부 항목을 계속 처리할 수 있습니다.  
  
> [!NOTE]
>  “내 코드만”이 사용하도록 설정된 경우 Visual Studio가 예외를 발생시키는 줄에서 중단하고 "예외가 사용자 코드에서 처리되지 않았다"는 오류 메시지를 표시합니다. 이 오류는 심각하지는 않습니다. F5 키를 눌러 계속하고 이러한 예제에 설명된 예외 처리 동작을 확인할 수 있습니다. 맨 처음 오류 지점에서 Visual Studio가 실행을 중단하지 않도록 하려면 **도구, 옵션, 디버깅, 일반** 을 차례로 선택하고 **내 코드만 사용**확인란의 선택을 취소하기만 하면 됩니다.  
  
## <a name="attached-child-tasks-and-nested-aggregateexceptions"></a>연결된 자식 작업 및 중첩된 AggregateExceptions  
 작업에 예외를 throw하는 연결된 자식 작업이 있는 경우 해당 예외가 <xref:System.AggregateException> 에서 래핑된 다음 상위 작업으로 전파되고, 이 상위 작업은 해당 예외를 자체 <xref:System.AggregateException> 에서 래핑한 다음 호출 스레드로 다시 전파합니다. 이러한 경우에는 <xref:System.AggregateException.InnerExceptions%2A> 의 속성에서 <xref:System.AggregateException> 에서 발견 된 예외는 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> 또는 <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` 또는 <xref:System.Threading.Tasks.Task.WaitAny%2A> 또는 <xref:System.Threading.Tasks.Task.WaitAll%2A> 메서드 하나 이상 포함 <xref:System.AggregateException> 인스턴스 하지는 오류를 발생 시킨 원래 예외가 있습니다. 반복할 필요가 없도록 하려면 중첩 된 <xref:System.AggregateException> 예외를 제외 하면 צ ְ ײ는 <xref:System.AggregateException.Flatten%2A> 메서드를 모두 제거 하는 중첩 된 <xref:System.AggregateException> 예외를 있도록는 <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> 속성에 원래 예외가 포함 합니다. 다음 예제에서는 중첩된 <xref:System.AggregateException> 인스턴스가 하나의 루프에서 결합되고 처리됩니다.  
  
 [!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
 [!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]  
  
 사용할 수도 있습니다는 <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> 메서드 다중에서 내부 예외를 다시 throw 할 <xref:System.AggregateException> 인스턴스에서 단일에서 여러 작업에서 throw 된 <xref:System.AggregateException> 다음 예제와 같이 인스턴스.  
  
 [!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
 [!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]  
  
## <a name="exceptions-from-detached-child-tasks"></a>분리된 자식 작업의 예외  
 기본적으로 자식 작업은 분리된 작업으로 만들어집니다. 분리된 작업에서 throw된 예외는 직계 부모 작업에서 처리되거나 다시 throw되어야 하지만, 연결된 자식 작업이 다시 전파되는 것과 동일한 방식으로 호출 스레드에 다시 전파되지는 않습니다. 최상위 부모는 분리된 자식의 예외를 수동으로 다시 throw하여 <xref:System.AggregateException> 에서 래핑하고 호출 스레드로 다시 전파할 수 있습니다.  
  
 [!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
 [!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]  
  
 연속을 사용하여 자식 작업에서 예외를 계속 관찰하는 경우에도 해당 예외는 여전히 부모 작업에서 관찰해야 합니다.  
  
## <a name="exceptions-that-indicate-cooperative-cancellation"></a>협조적 취소를 나타내는 예외  
 작업의 사용자 코드가 취소 요청에 응답하는 경우, 올바른 절차는 요청을 통신한 취소 토큰을 전달하는 <xref:System.OperationCanceledException> 을 throw하는 것입니다. 예외를 전파하려고 시도하기 전에 작업 인스턴스가 요청이 만들어졌을 때 요청에 전달된 토큰과 예외의 토큰을 비교합니다. 두 토큰이 동일한 경우 작업은 <xref:System.Threading.Tasks.TaskCanceledException> 에서 래핑된 <xref:System.AggregateException>을 전파하며 이는 내부 예외를 검사할 때 확인할 수 있습니다. 그러나 호출 스레드가 작업을 기다리지 않는 경우 이 특정 예외는 전파되지 않습니다. 자세한 내용은 [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md)을 참조하세요.  
  
 [!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
 [!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]  
  
## <a name="using-the-handle-method-to-filter-inner-exceptions"></a>핸들 메서드를 사용하여 내부 예외 필터링  
 사용할 수는 <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> 메서드를 추가 논리를 사용 하지 않고 "처리 됨"으로 처리할 수 있는 예외를 필터링 합니다. 에 제공 되는 사용자 대리자에는 <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType> 메서드를 예외 형식을 검사할 수 있습니다는 <xref:System.Exception.Message%2A> 속성 또는 무해 한지 여부를 확인할 수 있는 항목에 대 한 기타 정보입니다. 대리자 반환 하는 모든 예외 `false` 를 새로운 다시 throw 됩니다 <xref:System.AggregateException> 후 즉시 인스턴스는 <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> 메서드 반환 합니다.  
  
 다음 예제에서 각 예외를 검사 하는이 항목의 첫 번째 예제와 기능적으로 동일는 <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> 컬렉션입니다.  이 예외 처리기가 호출 하는 대신,는 <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> 대 한 각 예외 및 되지 않는 예외만 메서드 개체 `CustomException` 인스턴스.  
  
 [!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
 [!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]  
  
 다음은 사용 하는 전체 예제는 <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> 에 대 한 특수 처리를 제공 하는 메서드는 <xref:System.UnauthorizedAccessException> 파일을 열거 하는 동안 예외가 발생 했습니다.  
  
 [!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
 [!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]  
  
<a name="ExceptionProp"></a>   
## <a name="observing-exceptions-by-using-the-taskexception-property"></a>Task.Exception 속성을 사용하여 예외 관찰  
 작업이 완료 된 경우에 <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> 상태에 해당 <xref:System.Threading.Tasks.Task.Exception%2A> 오류를 발생 시킨 특정 예외를 검색 하도록 속성을 검사할 수 있습니다. <xref:System.Threading.Tasks.Task.Exception%2A> 속성을 관찰하는 좋은 방법은 다음 예제에 나와 있는 것처럼 선행 작업에서 오류가 발생할 경우에만 실행되는 연속을 사용하는 것입니다.  
  
 [!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
 [!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]  
  
 실제 응용 프로그램에서 연속 대리자는 예외에 대한 자세한 정보를 기록하고 새 작업을 생성하여 예외에서 복구할 수도 있습니다.  
  
## <a name="unobservedtaskexception-event"></a>UnobservedTaskException 이벤트  
 일부 시나리오에서는 예를 들어 신뢰할 수 없는 플러그인을 호스트할 때 무해한 예외가 자주 발생할 수 있으며 그 모든 예외를 수동으로 관찰하는 것은 어려울 수 있습니다. 이러한 경우 처리할 수 있습니다는 <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType> 이벤트입니다. <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType> 관찰 되지 않은 예외가 가입 된 스레드로 다시 전파 되지 않도록 방지 하기 위해 처리기에 전달 되는 인스턴스를 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
