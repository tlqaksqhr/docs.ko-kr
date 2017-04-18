---
title: "Introduction to PLINQ | Microsoft Docs"
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
  - "PLINQ queries, introduction to"
ms.assetid: eaa720d8-8999-4eb7-8df5-3c19ca61cad0
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# Introduction to PLINQ
## 병렬 쿼리 정의  
 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)]에는 언어 통합 쿼리\(LINQ\)가 포함되어 있습니다.  형식 안전 방식으로 <xref:System.Collections.IEnumerable?displayProperty=fullName> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName> 데이터 소스를 쿼리하기 위한 통합 모델을 갖추고 있습니다.  LINQ to Objects는 <xref:System.Collections.Generic.List%601> 및 배열과 같은 메모리 내 컬렉션에 대해 실행되는 LINQ 쿼리의 이름입니다.  이 문서에서는 사용자가 LINQ의 기본적인 개념을 이해하고 있다고 가정합니다.  자세한 내용은 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)을 참조하십시오.  
  
 PLINQ\(병렬 LINQ\)는 LINQ 패턴의 병렬 구현입니다.  PLINQ 쿼리는 여러 가지 면에서 비병렬 LINQ to Objects 쿼리와 유사합니다.  PLINQ 쿼리는 순차적 [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] 쿼리와 마찬가지로 메모리 내 <xref:System.Collections.IEnumerable> 또는 <xref:System.Collections.Generic.IEnumerable%601> 데이터 소스에 대해 작동하며 지연된 실행을 사용합니다. 즉, 쿼리가 열거될 때까지 실행이 시작되지 않습니다.  주요 차이점은 PLINQ에서는 시스템의 모든 프로세서를 최대한으로 활용하려고 한다는 점입니다.  이를 위해 PLINQ에서는 데이터 소스를 여러 세그먼트로 분할한 다음 개별 작업자 스레드에 있는 각 세그먼트에 대한 쿼리를 여러 프로세서에서 병렬로 실행합니다.  대부분의 경우 쿼리를 병렬로 실행하면 실행 속도가 상당히 빨라집니다.  
  
 일부 쿼리 유형의 경우 PLINQ를 사용하면 병렬 실행을 통해 레거시 코드를 사용할 때보다 성능을 크게 향상시킬 수 있습니다. 일반적으로 데이터 소스에 <xref:System.Linq.ParallelEnumerable.AsParallel%2A> 쿼리 작업을 추가하기만 하면 됩니다.  그러나 병렬 처리에는 복잡한 과정이 필요하므로 일부 쿼리 작업은 PLINQ를 사용할 경우 더 느리게 실행될 수도 있습니다.  일부 쿼리는 실제로 병렬화함으로써 속도가 더 느려집니다.  따라서 순서 지정 등의 문제가 병렬 쿼리에 주는 영향을 이해하고 있어야 합니다.  자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)을 참조하십시오.  
  
> [!NOTE]
>  이 문서에서는 람다 식을 사용하여 PLINQ에 대리자를 정의합니다.  C\# 또는 Visual Basic의 람다 식에 익숙하지 않으면 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)을 참조하십시오.  
  
 이 문서에서는 주요 PLINQ 클래스에 대해 간략히 설명하고 PLINQ 쿼리를 만드는 방법에 대해 설명합니다.  각 단원에는 보다 자세한 정보와 코드 예제를 볼 수 있는 링크가 포함되어 있습니다.  
  
## ParallelEnumerable 클래스  
 <xref:System.Linq.ParallelEnumerable?displayProperty=fullName> 클래스는 PLINQ의 거의 모든 기능을 노출합니다.  이 클래스와 <xref:System.Linq?displayProperty=fullName> 네임스페이스의 나머지 형식은 System.Core.dll 어셈블리로 컴파일됩니다.  Visual Studio의 기본 C\# 및 Visual Basic 프로젝트는 모두 이 어셈블리를 참조하고 이 네임스페이스를 가져옵니다.  
  
 <xref:System.Linq.ParallelEnumerable>은 LINQ to Objects에서 지원하는 표준 쿼리 연산자를 각각 병렬화하려고 하지는 않지만 이러한 연산자의 구현을 포함합니다.  [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)]에 익숙하지 않을 경우에는 [Introduction to LINQ](../../../ocs/visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)를 참조하십시오.  
  
 <xref:System.Linq.ParallelEnumerable> 클래스에는 표준 쿼리 연산자 외에도 병렬 실행과 관련된 동작을 사용할 수 있게 해 주는 일련의 메서드가 포함되어 있습니다.  다음 표에서는 이러한 PLINQ 관련 메서드를 보여 줍니다.  
  
|ParallelEnumerable 연산자|설명|  
|----------------------------|--------|  
|<xref:System.Linq.ParallelEnumerable.AsParallel%2A>|PLINQ의 진입점입니다.  가능한 경우 쿼리의 나머지 부분이 병렬화되도록 지정합니다.|  
|<xref:System.Linq.ParallelEnumerable.AsSequential%2A>|쿼리의 나머지 부분이 비병렬 LINQ 쿼리처럼 순차적으로 실행되도록 지정합니다.|  
|<xref:System.Linq.ParallelEnumerable.AsOrdered%2A>|orderby\(Vlsual Basic의 경우 Order By\) 절을 사용하는 등의 방법으로 PLINQ에서 쿼리의 나머지 부분에 대해 또는 순서가 변경될 때까지 소스 시퀀스의 순서를 유지하도록 지정합니다.|  
|<xref:System.Linq.ParallelEnumerable.AsUnordered%2A>|PLINQ에서 쿼리의 나머지 부분에 대해 소스 시퀀스의 순서를 유지할 필요가 없도록 지정합니다.|  
|<xref:System.Linq.ParallelEnumerable.WithCancellation%2A>|PLINQ에서 제공된 취소 토큰을 정기적으로 모니터링하고 취소가 요청된 경우 실행을 취소하도록 지정합니다.|  
|<xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A>|PLINQ에서 쿼리를 병렬화하는 데 사용할 최대 프로세서 수를 지정합니다.|  
|<xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>|가능한 경우 PLINQ에서 병렬 결과를 다시 소비 스레드의 한 시퀀스에만 병합하는 방법에 대한 힌트를 제공합니다.|  
|<xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A>|기본 동작이 쿼리를 순차적으로 실행하는 것인 경우에도 PLINQ에서 쿼리를 병렬화할지 여부를 지정합니다.|  
|<xref:System.Linq.ParallelEnumerable.ForAll%2A>|쿼리 결과를 반복할 때와는 달리 결과를 먼저 소비 스레드에 다시 병합하지 않고 병렬로 처리할 수 있도록 하는 다중 스레드 열거형 메서드입니다.|  
|<xref:System.Linq.ParallelEnumerable.Aggregate%2A> 오버로드|PLINQ에 고유한 오버로드로서, 스레드 로컬 파티션에 대한 중간 집계와 모든 파티션의 결과를 결합하는 최종 집계 함수를 사용할 수 있게 해 줍니다.|  
  
## 옵트인\(Opt In\) 모델  
 쿼리를 작성하는 경우 다음 예제와 같이 데이터 소스의 <xref:System.Linq.ParallelEnumerable.AsParallel%2A?displayProperty=fullName> 확장 메서드를 호출하여 PLINQ에 옵트인\(opt in\)합니다.  
  
 [!code-csharp[PLINQ#1](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#1)]
 [!code-vb[PLINQ#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#1)]  
  
 <xref:System.Linq.ParallelEnumerable.AsParallel%2A> 확장 메서드는 후속 쿼리 연산자\(이 경우 `where` 및 `select`\)를 <xref:System.Linq.ParallelEnumerable?displayProperty=fullName> 구현에 바인딩합니다.  
  
## 실행 모드  
 기본적으로 PLINQ는 보수적입니다.  런타임에 PLINQ 인프라에서는 쿼리의 전반적인 구조를 분석합니다.  병렬화를 통해 쿼리 속도가 향상될 수 있으면 PLINQ에서는 소스 시퀀스를 동시에 실행할 수 있는 여러 작업으로 분할합니다.  쿼리를 병렬화하는 것이 안전하지 않은 경우 PLINQ에서는 쿼리를 순차적으로만 실행합니다.  부담이 클 수 있는 병렬 알고리즘이나 부담이 적은 순차적 알고리즘 중에서 선택할 수 있는 경우 PLINQ에서는 기본적으로 순차적 알고리즘을 선택합니다.  <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> 메서드와 <xref:System.Linq.ParallelExecutionMode?displayProperty=fullName> 열거형을 사용하면 PLINQ에서 병렬 알고리즘을 선택하도록 지정할 수 있습니다.  이 방법은 테스트와 측정을 통해 특정 쿼리가 병렬 모드에서 더 빠르게 실행되는 것으로 확인된 경우에 유용합니다.  자세한 내용은 [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)을 참조하십시오.  
  
## 병렬 처리 수준  
 기본적으로 PLINQ에서는 호스트 컴퓨터의 모든 프로세서\(최대 64개\)를 사용합니다.  <xref:System.Linq.ParallelEnumerable.WithDegreeOfParallelism%2A> 메서드를 사용하면 PLINQ에서 프로세서를 지정된 수 이하로만 사용하도록 할 수 있습니다.  이 방법은 컴퓨터에서 실행 중인 다른 프로세스가 일정량의 CPU 시간을 받도록 하려는 경우에 유용합니다.  다음 코드 조각에서는 최대 2개의 프로세서를 사용하도록 쿼리를 제한합니다.  
  
 [!code-csharp[PLINQ#5](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#5)]
 [!code-vb[PLINQ#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#5)]  
  
 쿼리에서 파일 I\/O와 같이 CPU 바인딩되지 않은 작업을 상당히 많이 수행할 경우에는 병렬 처리 수준을 컴퓨터의 코어 수보다 높게 지정하는 것이 좋을 수 있습니다.  
  
## 순서가 지정된 병렬 쿼리와 순서가 지정되지 않은 병렬 쿼리 비교  
 일부 쿼리의 경우 쿼리 연산자가 생성하는 결과에서 소스 시퀀스의 순서를 유지해야 합니다.  PLINQ에서는 이를 위해 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 연산자를 제공합니다.  <xref:System.Linq.ParallelEnumerable.AsOrdered%2A>는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A>과는 다릅니다.  <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 시퀀스는 여전히 병렬로 처리되지만 해당 결과가 버퍼링되고 정렬됩니다.  순서 유지를 위해서는 일반적으로 추가 작업이 필요하므로 <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> 시퀀스는 기본 <xref:System.Linq.ParallelEnumerable.AsUnordered%2A> 시퀀스보다 느리게 처리될 수 있습니다.  특정 작업을 순서가 지정된 병렬 처리로 실행할 경우 순차적으로 실행할 때보다 속도가 빨라질지 여부는 여러 요인에 따라 결정됩니다.  
  
 다음 코드 예제에서는 순서 유지 기능을 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[PLINQ#3](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#3)]
 [!code-vb[PLINQ#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#3)]  
  
 자세한 내용은 [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)을 참조하십시오.  
  
## 병렬 쿼리와 순차적 쿼리 비교  
 일부 작업에서는 소스 데이터가 순차적으로 전달되어야 합니다.  <xref:System.Linq.ParallelEnumerable> 쿼리 연산자는 필요할 경우 자동으로 순차 모드로 되돌립니다.  순차적으로 실행해야 하는 사용자 정의 쿼리 연산자 및 사용자 대리자를 위해 PLINQ에서는 <xref:System.Linq.ParallelEnumerable.AsSequential%2A> 메서드를 제공합니다.  <xref:System.Linq.ParallelEnumerable.AsSequential%2A>을 사용할 경우 쿼리의 모든 후속 연산자는 <xref:System.Linq.ParallelEnumerable.AsParallel%2A>이 다시 호출될 때까지 순차적으로 실행됩니다.  자세한 내용은 [How to: Combine Parallel and Sequential LINQ Queries](../../../docs/standard/parallel-programming/how-to-combine-parallel-and-sequential-linq-queries.md)을 참조하십시오.  
  
## 쿼리 결과 병합 옵션  
 PLINQ 쿼리가 병렬로 실행될 경우 각 작업자 스레드의 결과는 `foreach` 루프\([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `For Each`\)에서 사용하거나 목록 또는 배열에 삽입할 수 있도록 주 스레드에 다시 병합되어야 합니다.  일부 경우에는 결과 생성을 보다 빨리 시작하는 옵션과 같이 특정 종류의 병합 옵션을 지정하는 것이 좋을 수 있습니다.  이를 위해 PLINQ에서는 <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> 메서드와 <xref:System.Linq.ParallelMergeOptions> 열거형을 지원합니다.  자세한 내용은 [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)을 참조하십시오.  
  
## ForAll 연산자  
 순차적 [!INCLUDE[vbteclinq](../../../includes/vbteclinq-md.md)] 쿼리에서는 쿼리가 `foreach`\([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]의 경우 `For Each`\) 루프에서 열거되거나 <xref:System.Linq.ParallelEnumerable.ToList%2A>, <xref:System.Linq.ParallelEnumerable.ToArray%2A> 또는 <xref:System.Linq.ParallelEnumerable.ToDictionary%2A> 등의 메서드를 호출하여 열거될 때까지 실행이 지연됩니다.  PLINQ에서는 `foreach`를 사용하여 쿼리를 실행하고 결과를 반복할 수도 있습니다.  그러나 `foreach` 자체는 병렬로 실행되지 않으므로 모든 병렬 작업의 출력을 해당 루프가 실행되는 스레드에 다시 병합해야 합니다.  PLINQ에서는 쿼리 결과의 최종 순서를 유지해야 할 때와, 각 요소에 대해 `Console.WriteLine`을 호출하는 경우와 같이 순차적 방식으로 결과를 처리해야 할 때마다 `foreach`를 사용할 수 있습니다.  순서를 유지할 필요가 없고 결과 처리 자체를 병렬화할 수 있는 경우 쿼리를 보다 빠르게 실행하려면 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 메서드를 사용하여 PLINQ 쿼리를 실행합니다.  <xref:System.Linq.ParallelEnumerable.ForAll%2A>에서는 이 최종 병합 단계를 수행하지 않습니다.  다음 코드 예제에서는 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 메서드를 사용하는 방법을 보여 줍니다.  여기서는 항목을 제거하려 시도하지 않고 여러 스레드를 동시에 추가할 수 있도록 최적화된 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>을 사용합니다.  
  
 [!code-csharp[PLINQ#4](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#4)]
 [!code-vb[PLINQ#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#4)]  
  
 다음 그림에서는 쿼리 실행과 관련하여 `foreach`와 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 간의 차이점을 보여 줍니다.  
  
 ![ForAll 및 Foreach 비교](../../../docs/standard/parallel-programming/media/vs-isvnt-allvseach.png "VS\_ISVNT\_ALLvsEACH")  
  
## 취소  
 PLINQ는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]의 취소 형식과 통합되어 있습니다. 자세한 내용은 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)을 참조하십시오. 따라서 순차적 LINQ to Objects 쿼리와 달리 PLINQ 쿼리는 취소할 수 있습니다.  취소할 수 있는 PLINQ 쿼리를 만들려면 쿼리에 <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> 연산자를 사용하거나 <xref:System.Threading.CancellationToken> 인스턴스를 인수로 제공합니다.  토큰의 <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> 속성이 true로 설정되어 있으면 PLINQ에서는 이를 인식하여 모든 스레드에서의 처리를 중지하고 <xref:System.OperationCanceledException>을 throw합니다.  
  
 취소 토큰이 설정된 뒤에도 PLINQ 쿼리에서 일부 요소의 처리를 계속 진행할 수 있습니다.  
  
 응답성을 높이기 위해 장기 실행 사용자 대리자에서 취소 요청에 응답할 수도 있습니다.  자세한 내용은 [How to: Cancel a PLINQ Query](../../../docs/standard/parallel-programming/how-to-cancel-a-plinq-query.md)을 참조하십시오.  
  
## 예외  
 PLINQ 쿼리가 실행될 때 여러 예외가 서로 다른 스레드에서 동시에 throw될 수 있습니다.  또한 예외를 처리하는 코드와 예외를 throw한 코드가 서로 다른 스레드에 있을 수도 있습니다.  PLINQ에서는 <xref:System.AggregateException> 형식을 사용하여 쿼리에서 throw된 모든 예외를 캡슐화하고 이러한 예외를 호출 스레드로 다시 마샬링합니다.  호출 스레드에서는 하나의 try\-catch 블록만 필요합니다.  그러나 <xref:System.AggregateException>에 캡슐화된 모든 예외를 반복하고 안전하게 복원할 수 있는 예외를 catch할 수 있습니다.  드물기는 하지만 <xref:System.AggregateException>에 래핑되지 않은 예외가 throw되는 경우도 있으며, <xref:System.Threading.ThreadAbortException>도 래핑되지 않습니다.  
  
 조인하는 스레드까지 버블링할 수 있도록 예외가 허용되는 경우 예외가 발생한 후에도 쿼리에서 일부 항목을 계속하여 처리할 수 있습니다.  
  
 자세한 내용은 [How to: Handle Exceptions in a PLINQ Query](../../../docs/standard/parallel-programming/how-to-handle-exceptions-in-a-plinq-query.md)을 참조하십시오.  
  
## 사용자 지정 파티셔너  
 일부 경우 소스 데이터의 일부 특성을 사용하는 사용자 지정 파티셔너를 작성하여 쿼리 성능을 향상시킬 수 있습니다.  쿼리에서 사용자 지정 파티셔너는 그 자체가 쿼리되는 열거 가능한 개체입니다.  
  
 [!code-csharp[PLINQ#2](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinq2_cs.cs#2)]
 [!code-vb[PLINQ#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq3.vb#2)]  
  
 PLINQ에서는 고정된 수의 파티션을 지원합니다. 단, 런타임에는 부하 분산을 위해 해당 파티션에 데이터가 동적으로 다시 할당될 수도 있습니다.  <xref:System.Threading.Tasks.Parallel.For%2A> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A>에서는 동적 분할만 지원되므로 런타임에 파티션 수가 변경됩니다.  자세한 내용은 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)을 참조하십시오.  
  
## PLINQ 성능 측정  
 대부분의 경우 쿼리를 병렬화할 수 있지만 이때 얻을 수 있는 성능상의 이점보다는 병렬 쿼리를 설정하는 데 필요한 오버헤드를 우선적으로 고려해야 합니다.  쿼리에서 수행하는 계산 과정이 많지 않거나 데이터 소스가 작은 경우에는 PLINQ 쿼리가 순차적 LINQ to Objects 개체보다도 느릴 수 있습니다.  Visual Studio Team Server의 병렬 성능 분석기를 사용하여 다양한 쿼리의 성능을 비교하고, 처리 병목 지점을 찾고, 쿼리를 병렬로 실행할지 순차적으로 실행할지를 결정할 수 있습니다.  자세한 내용은 [동시성 시각화 도우미](../Topic/Concurrency%20Visualizer.md) 및 [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)를 참조하십시오.  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)