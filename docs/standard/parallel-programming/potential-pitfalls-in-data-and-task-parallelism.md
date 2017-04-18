---
title: "Potential Pitfalls in Data and Task Parallelism | Microsoft Docs"
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
  - "parallel programming, pitfalls"
ms.assetid: 1e357177-e699-4b8f-9e49-56d3513ed128
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Potential Pitfalls in Data and Task Parallelism
대부분의 경우 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>를 사용하면 일반적인 순차적 루프를 사용할 때보다 성능이 크게 향상됩니다.  그러나 루프를 병렬화하는 작업은 복잡하며 이로 인해 순차적 코드에서는 보통 발생하지 않거나 전혀 발생하지 않는 문제가 유발될 수 있습니다.  이 항목에서는 병렬 루프를 작성할 때 주의해야 할 사항을 설명합니다.  
  
## 병렬화한다고 해서 속도가 항상 빨라지지는 않습니다.  
 경우에 따라서는 병렬 루프가 순차적 루프보다 느리게 실행될 수도 있습니다.  경험적으로, 반복의 수가 매우 적으면서 빠른 사용자 대리자를 사용하는 병렬 루프는 속도가 크게 개선될 가능성이 없습니다.  그러나 성능에는 많은 요인이 관련되므로 항상 실제 결과를 측정하는 것이 좋습니다.  
  
## 공유 메모리 위치에 쓰기 작업을 수행하지 마십시오.  
 순차적 코드에서는 정적 변수 또는 클래스 필드에 대한 읽기 또는 쓰기를 수행하는 것이 일반적입니다.  하지만 여러 스레드에서 이러한 변수에 동시에 액세스할 때마다 경합 조건이 발생할 가능성이 큽니다.  잠금을 사용하여 변수에 대한 액세스를 동기화할 수는 있지만 이 경우 성능이 악화될 수 있습니다.  따라서 병렬 루프의 공유 상태에 대한 액세스를 가능한 한 피하거나 제한하는 것이 좋습니다.  이렇게 하기 위한 가장 좋은 방법은 루프 실행 중에 <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> 변수를 사용하여 스레드 로컬 상태를 저장하는 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>의 오버로드를 사용하는 것입니다.  자세한 내용은 [How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) 및 [How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md)를 참조하십시오.  
  
## 과도하게 병렬화하지 마십시오.  
 병렬 루프를 사용하면 소스 컬렉션을 분할하고 작업자 스레드를 동기화하기 위한 오버헤드가 발생합니다.  병렬화의 이점은 컴퓨터의 프로세서 수에 따라 제한적입니다.  즉, 단일 프로세서에서 CPU 바인딩된 스레드를 여러 개 실행할 경우에는 속도가 향상되지 않습니다.  따라서 루프를 과도하게 병렬화하지 않도록 주의해야 합니다.  
  
 과도한 병렬화는 중첩 루프 내부에서 가장 자주 발생할 수 있습니다.  대부분의 경우 다음과 같은 조건이 하나 이상 해당되지 않으면 외부 루프만 병렬화하는 것이 좋습니다.  
  
-   내부 루프가 매우 깁니다.  
  
-   각 주문에 대해 부담이 큰 계산을 수행해야 하는 경우. 예제에 표시된 작업은 부담이 크지 않습니다.  
  
-   `cust.Orders`에 대한 쿼리를 병렬화하여 생성되는 스레드 수를 처리하기에 충분한 프로세서가 대상 시스템에 있는 경우  
  
 어느 경우든 최적의 쿼리 형태를 결정하는 가장 좋은 방법은 테스트 및 측정을 수행하는 것입니다.  
  
## 스레드로부터 안전하지 않은 메서드는 호출하지 마십시오.  
 병렬 루프에서 스레드로부터 안전하지 않은 인스턴스 메서드에 쓰기를 수행하면 데이터가 손상될 수 있으며 이러한 데이터 손상은 프로그램에서 발견될 수도 있지만 발견되지 않을 수도 있습니다.  또한 예외가 발생할 수도 있습니다.  다음 예제에서는 여러 스레드에서 동시에 <xref:System.IO.FileStream.WriteByte%2A?displayProperty=fullName> 메서드를 호출하려고 하지만 해당 클래스에서는 동시 호출이 지원되지 않습니다.  
  
 [!code-csharp[TPL_Pitfalls#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#04)]
 [!code-vb[TPL_Pitfalls#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#04)]  
  
## 스레드로부터 안전한 메서드에 대한 호출을 제한하십시오.  
 .NET Framework의 정적 메서드는 대부분 스레드로부터 안전하며 여러 스레드에서 동시에 호출될 수 있습니다.  그러나 이 경우에도 동기화가 수반되므로 쿼리의 속도가 상당히 느려질 수 있습니다.  
  
> [!NOTE]
>  쿼리에 <xref:System.Console.WriteLine%2A>에 대한 호출을 몇 개 삽입하면 이를 직접 테스트할 수 있습니다.  설명서의 예제에서는 예시 목적으로 이 메서드를 사용하지만 필요한 경우가 아니면 병렬 루프에서 이 메서드를 사용하면 안 됩니다.  
  
## 스레드 선호도 문제를 고려하십시오.  
 STA\(단일 스레드 아파트\), Windows Forms 및 WPF\(Windows Presentation Foundation\)에 대한 COM 상호 운용성과 같은 일부 기술은 코드가 특정 스레드에서 실행되어야 하는 스레드 선호도 제한을 적용합니다.  예를 들어 Windows Forms 및 WPF 모두에서 컨트롤은 해당 컨트롤이 만들어진 스레드에서만 액세스할 수 있습니다.  따라서 UI 스레드에서만 작업을 예약하도록 스레드 스케줄러를 구성하지 않은 경우에는 병렬 루프에서 목록 컨트롤을 업데이트할 수 없습니다.  자세한 내용은 [How to: Schedule Work on the User Interface \(UI\) Thread](../Topic/How%20to:%20Schedule%20Work%20on%20the%20User%20Interface%20\(UI\)%20Thread.md)을 참조하십시오.  
  
## Parallel.Invoke에 의해 호출되는 대리자에서 대기하는 동작은 신중하게 구현하십시오.  
 특정 상황에서 작업 병렬 라이브러리는 작업을 인라인으로 실행합니다. 즉, 현재 실행 중인 스레드에서 작업을 실행합니다. 자세한 내용은 [Task Schedulers](../Topic/Task%20Schedulers.md)을 참조하십시오. 이를 통해 성능이 최적화되지만 경우에 따라서는 교착 상태가 발생할 수 있습니다.  예를 들어, 두 작업은 동일한 대리자 코드를 실행할 수 있습니다. 이 코드는 이벤트 발생 시 신호를 보낸 후 다른 작업에서 신호를 보내기를 기다립니다.  두 번째 작업이 첫 번째 작업과 동일한 스레드에서 인라인으로 실행되고 첫 번째 작업이 대기 상태로 전환되면 두 번째 작업은 이벤트에 대한 신호를 보내지 못합니다.  이러한 상황이 발생하지 않도록 하려면 대기 작업에 대해 제한 시간을 지정하거나 특정 작업이 다른 작업을 차단할 수 없도록 명시적인 스레드 생성자를 사용하면 됩니다.  
  
## ForEach, For 및 ForAll의 반복이 항상 병렬로 실행되는 것은 아닙니다.  
 <xref:System.Threading.Tasks.Parallel.For%2A>, <xref:System.Threading.Tasks.Parallel.ForEach%2A> 또는 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 루프의 개별 반복이 병렬로 실행될 수도 있지만 반드시 그런 것은 아니라는 점을 명심할 필요가 있습니다.  따라서 반복이 병렬로 실행되거나 반복이 특정 순서로 실행되어야만 정확성이 보장되는 코드는 작성하지 말아야 합니다.  예를 들어 다음과 같은 코드는 교착 상태를 가져올 수 있습니다.  
  
 [!code-csharp[TPL_Pitfalls#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#01)]
 [!code-vb[TPL_Pitfalls#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#01)]  
  
 이 예제에서 한 반복은 이벤트를 설정하고 다른 모든 반복은 이벤트를 기다립니다.  이벤트를 설정하는 반복이 완료되기 전까지는 대기 중인 어떠한 반복도 완료할 수 없습니다.  그러나 이벤트 설정 반복을 실행하기도 전에 병렬 루프를 실행하는 데 사용되는 모든 스레드가 이벤트 대기 반복에 의해 차단될 수 있습니다.  그 결과로 교착 상태가 발생합니다. 이벤트 설정 반복은 결코 실행될 수 없고 대기 중인 반복은 활성화될 수 없기 때문입니다.  
  
 특히 병렬 루프의 특정 반복이 루프의 다른 반복이 진행되기를 기다리는 일이 없어야 합니다.  병렬 루프에서 반복을 순차적으로 진행하도록 예약한 경우 그 순서가 반대가 되면 교착 상태가 발생할 수 있습니다.  
  
## 병렬 루프가 UI 스레드에서 실행되지 않도록 하십시오.  
 응용 프로그램의 UI\(사용자 인터페이스\)가 반응성을 유지하도록 해야 합니다.  병렬화가 필요한 만큼의 작업이 연산에 포함된 경우 해당 연산을 UI 스레드에서 실행하지 않아야 합니다.  대신, 연산이 백그라운드 스레드에서 실행되도록 오프로드해야 합니다.  예를 들어, 나중에 UI 컨트롤로 렌더링되어야 하는 일부 데이터를 계산하는 데 병렬 루프를 사용하려는 경우 해당 루프를 UI 이벤트 처리기에서 직접 실행하는 대신 작업 인스턴스 내에서 실행하는 것을 고려해야 합니다.  코어 계산이 완료된 경우에만 UI 업데이트를 UI 스레드로 다시 마샬링해야 합니다.  
  
 UI 스레드에서 병렬 루프를 실행하는 경우 병렬 루프 내에서 UI 컨트롤을 업데이트하지 않도록 주의해야 합니다.  UI 스레드에서 실행 중인 병렬 루프 내에서 UI 컨트롤을 업데이트하려고 하면 UI 업데이트의 호출 방법에 따라 상태 손상, 예외, 지연된 업데이트는 물론 교착 상태까지 발생할 수 있습니다.  다음 예제에서 병렬 루프는 모든 반복이 완료될 때까지 해당 루프가 실행 중인 UI 스레드를 차단합니다.  그러나 <xref:System.Threading.Tasks.Parallel.For%2A>와 같이 해당 루프의 반복이 백그라운드 스레드에서 실행되는 경우에는 Invoke 호출에 따라 메시지가 UI 스레드로 제출되며 이 메시지의 처리를 기다리는 동안 차단됩니다.  UI 스레드는 <xref:System.Threading.Tasks.Parallel.For%2A> 실행 중에 차단되기 때문에 메시지는 처리될 수 없고 UI 스레드는 교착 상태에 있게 됩니다.  
  
 [!code-csharp[TPL_Pitfalls#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#02)]
 [!code-vb[TPL_Pitfalls#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#02)]  
  
 다음 예제에서는 작업 인스턴스 내에서 루프를 실행하여 교착 상태를 방지하는 방법을 보여 줍니다.  이 방법에 따르면 UI 스레드는 루프에 의해 차단되지 않고 메시지가 처리될 수 있습니다.  
  
 [!code-csharp[TPL_Pitfalls#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_pitfalls/cs/pitfalls.cs#03)]
 [!code-vb[TPL_Pitfalls#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_pitfalls/vb/pitfalls_vb.vb#03)]  
  
## 참고 항목  
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [Potential Pitfalls with PLINQ](../../../docs/standard/parallel-programming/potential-pitfalls-with-plinq.md)   
 [Patterns for Parallel Programming: Understanding and Applying Parallel Patterns with the .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=185142)