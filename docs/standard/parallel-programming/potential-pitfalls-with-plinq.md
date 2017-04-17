---
title: "Potential Pitfalls with PLINQ | Microsoft Docs"
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
  - "PLINQ queries, pitfalls"
ms.assetid: 75a38b55-4bc4-488a-87d5-89dbdbdc76a2
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Potential Pitfalls with PLINQ
대부분의 경우 PLINQ를 사용하면 순차적 LINQ to Objects 쿼리를 사용할 때보다 성능이 크게 향상됩니다.  그러나 쿼리 실행을 병렬화하는 작업은 복잡하며 이로 인해 순차적 코드에서는 보통 발생하지 않거나 전혀 발생하지 않는 문제가 유발될 수 있습니다.  이 항목에서는 PLINQ 쿼리를 작성할 때 주의해야 할 사항을 설명합니다.  
  
## 병렬화한다고 해서 속도가 항상 빨라지지는 않습니다.  
 병렬화할 때 PLINQ 쿼리의 실행 속도가 LINQ to Objects 쿼리의 실행 속도보다 느려지는 경우도 있습니다.  경험적으로, 소스 요소의 수가 매우 적으면서 빠른 사용자 대리자를 사용하는 쿼리는 속도가 크게 개선될 가능성이 없습니다.  그러나 성능에는 많은 요인이 관련되므로 PLINQ를 사용할지 여부를 결정하기 전에 실제 결과를 측정하는 것이 좋습니다.  자세한 내용은 [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md)을 참조하십시오.  
  
## 공유 메모리 위치에 쓰기 작업을 수행하지 마십시오.  
 순차적 코드에서는 정적 변수 또는 클래스 필드에 대한 읽기 또는 쓰기를 수행하는 것이 일반적입니다.  하지만 여러 스레드에서 이러한 변수에 동시에 액세스할 때마다 경합 조건이 발생할 가능성이 큽니다.  잠금을 사용하여 변수에 대한 액세스를 동기화할 수는 있지만 이 경우 성능이 악화될 수 있습니다.  따라서 PLINQ 쿼리의 공유 상태에 대한 액세스를 가능한 한 피하거나 제한하는 것이 좋습니다.  
  
## 과도하게 병렬화하지 마십시오.  
 `AsParallel` 연산자를 사용하면 소스 컬렉션을 분할하고 작업자 스레드를 동기화하기 위한 오버헤드가 발생합니다.  병렬화의 이점은 컴퓨터의 프로세서 수에 따라 제한적입니다.  즉, 단일 프로세서에서 CPU 바인딩된 스레드를 여러 개 실행할 경우에는 속도가 향상되지 않습니다.  따라서 쿼리를 과도하게 병렬화하지 않도록 주의해야 합니다.  
  
 과도한 병렬화는 다음 코드 조각과 같이 중첩된 쿼리에서 발생하는 경우가 가장 많습니다.  
  
 [!code-csharp[PLINQ#20](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#20)]
 [!code-vb[PLINQ#20](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#20)]  
  
 이 경우 다음과 같은 조건이 하나 이상 해당되지 않으면 외부 데이터 소스\(customers\)만 병렬화하는 것이 좋습니다.  
  
-   내부 데이터 소스\(cust.Orders\)가 매우 긴 경우  
  
-   각 주문에 대해 부담이 큰 계산을 수행해야 하는 경우. 예제에 표시된 작업은 부담이 크지 않습니다.  
  
-   `cust.Orders`에 대한 쿼리를 병렬화하여 생성되는 스레드 수를 처리하기에 충분한 프로세서가 대상 시스템에 있는 경우  
  
 어느 경우든 최적의 쿼리 형태를 결정하는 가장 좋은 방법은 테스트 및 측정을 수행하는 것입니다.  자세한 내용은 [How to: Measure PLINQ Query Performance](../../../docs/standard/parallel-programming/how-to-measure-plinq-query-performance.md)을 참조하십시오.  
  
## 스레드로부터 안전하지 않은 메서드는 호출하지 마십시오.  
 PLINQ 쿼리에서 스레드로부터 안전하지 않은 인스턴스 메서드에 쓰기를 수행하면 데이터가 손상될 수 있으며 이러한 데이터 손상은 프로그램에서 발견될 수도 있지만 발견되지 않을 수도 있습니다.  또한 예외가 발생할 수도 있습니다.  다음 예제에서는 여러 스레드에서 동시에 `Filestream.Write` 메서드를 호출하려고 하지만 해당 클래스에서는 동시 호출이 지원되지 않습니다.  
  
```vb  
Dim fs As FileStream = File.OpenWrite(…)  
a.Where(...).OrderBy(...).Select(...).ForAll(Sub(x) fs.Write(x))  
```  
  
```csharp  
FileStream fs = File.OpenWrite(...);  
a.Where(...).OrderBy(...).Select(...).ForAll(x => fs.Write(x));  
```  
  
## 스레드로부터 안전한 메서드에 대한 호출을 제한하십시오.  
 .NET Framework의 정적 메서드는 대부분 스레드로부터 안전하며 여러 스레드에서 동시에 호출될 수 있습니다.  그러나 이 경우에도 동기화가 수반되므로 쿼리의 속도가 상당히 느려질 수 있습니다.  
  
> [!NOTE]
>  쿼리에 <xref:System.Console.WriteLine%2A>에 대한 호출을 몇 개 삽입하면 이를 직접 테스트할 수 있습니다.  이 문서의 예제에서는 예시 목적으로 이 메서드를 사용하지만 PLINQ 쿼리에 이 메서드를 사용하면 안 됩니다.  
  
## 불필요한 순서 지정 작업을 피하십시오.  
 PLINQ에서 병렬로 쿼리를 실행할 경우 소스 시퀀스는 여러 스레드에서 동시에 작동할 수 있는 여러 파티션으로 나뉩니다.  `OrderBy` 등의 연산자를 제외하고는 기본적으로 파티션이 처리되고 결과가 전달되는 순서를 예측할 수 없습니다.  PLINQ에서 소스 시퀀스의 순서가 유지되도록 할 수 있지만 이렇게 하면 성능에 부정적인 영향을 줄 수 있습니다.  최상의 방법은 가능한 경우 순서 유지가 사용되지 않도록 쿼리를 구조화하는 것입니다.  자세한 내용은 [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)을 참조하십시오.  
  
## 가능하면 ForEach 대신 ForAll을 사용하십시오.  
 PLINQ에서는 쿼리를 여러 스레드에서 실행하지만 `foreach` 루프\(Visual Basic의 경우 `For Each`\)의 결과를 사용할 경우에는 쿼리 결과를 다시 하나의 스레드로 병합한 다음 열거자를 통해 순차적으로 액세스해야 합니다.  이러한 과정이 불가피한 경우도 있지만 가능하면 `ForAll` 메서드를 사용하여 각 스레드에서 <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName>과 같이 스레드로부터 안전한 컬렉션에 쓰는 등의 방법으로 개별적으로 결과를 출력할 수 있도록 합니다.  
  
 같은 문제가 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 에도 적용됩니다. 즉, `source.AsParallel().Where().ForAll(...)` 은 강력하게 다음 중 하나로 선호되야 합니다.  
  
 `Parallel.ForEach(source.AsParallel().Where(), ...)`.  
  
## 스레드 선호도 문제를 고려하십시오.  
 STA\(단일 스레드 아파트\), Windows Forms 및 WPF\(Windows Presentation Foundation\)에 대한 COM 상호 운용성과 같은 일부 기술은 코드가 특정 스레드에서 실행되어야 하는 스레드 선호도 제한을 적용합니다.  예를 들어 Windows Forms 및 WPF 모두에서 컨트롤은 해당 컨트롤이 만들어진 스레드에서만 액세스할 수 있습니다.  디버거에서 실행 중인 경우 PLINQ 쿼리에서 Windows Forms 컨트롤의 공유 상태에 액세스하려고 하면 예외가 발생합니다. 이 설정은 해제할 수 있습니다. 그러나 쿼리가 UI 스레드에서 사용되는 경우에는 해당 코드가 한 스레드에서만 실행되므로 쿼리 결과를 열거하는 `foreach` 루프에서 컨트롤에 액세스할 수 있습니다.  
  
## ForEach, For 및 ForAll의 반복이 항상 병렬로 실행되는 것은 아닙니다.  
 <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName>, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 또는 <xref:System.Linq.ParallelEnumerable.ForAll%2A> 루프의 개별 반복이 병렬로 실행될 수도 있지만 반드시 그런 것은 아니라는 점을 명심할 필요가 있습니다.  따라서 반복이 병렬로 실행되거나 반복이 특정 순서로 실행되어야만 정확성이 보장되는 코드는 작성하지 말아야 합니다.  
  
 예를 들어 다음과 같은 코드는 교착 상태를 가져올 수 있습니다.  
  
```vb  
Dim mre = New ManualResetEventSlim()  
    Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll(Sub(j)   
  
                                                     If j = Environment.ProcessorCount Then  
  
                                                         Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Set()  
  
                                                     Else  
  
                                                         Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j)  
                                                         mre.Wait()  
                                                     End If  
    End Sub) ' deadlocks  
```  
  
```csharp  
ManualResetEventSlim mre = new ManualResetEventSlim();  
            Enumerable.Range(0, ProcessorCount * 100).AsParallel().ForAll((j) =>  
            {  
                if (j == Environment.ProcessorCount)  
                {  
                    Console.WriteLine("Set on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Set();  
                }  
                else  
                {  
                    Console.WriteLine("Waiting on {0} with value of {1}", Thread.CurrentThread.ManagedThreadId, j);  
                    mre.Wait();  
                }  
            }); //deadlocks  
```  
  
 이 예제에서 한 반복은 이벤트를 설정하고 다른 모든 반복은 이벤트를 기다립니다.  이벤트를 설정하는 반복이 완료되기 전까지는 대기 중인 어떠한 반복도 완료할 수 없습니다.  그러나 이벤트 설정 반복을 실행하기도 전에 병렬 루프를 실행하는 데 사용되는 모든 스레드가 이벤트 대기 반복에 의해 차단될 수 있습니다.  그 결과로 교착 상태가 발생합니다. 이벤트 설정 반복은 결코 실행될 수 없고 대기 중인 반복은 활성화될 수 없기 때문입니다.  
  
 특히 병렬 루프의 특정 반복이 루프의 다른 반복이 진행되기를 기다리는 일이 없어야 합니다.  병렬 루프에서 반복을 순차적으로 진행하도록 예약한 경우 그 순서가 반대가 되면 교착 상태가 발생할 수 있습니다.  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)