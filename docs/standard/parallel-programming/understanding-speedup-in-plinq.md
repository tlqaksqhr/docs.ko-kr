---
title: "Understanding Speedup in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, performance tuning"
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Understanding Speedup in PLINQ
PLINQ의 주 용도는 다중 코어 컴퓨터에서 쿼리 대리자를 병렬로 실행하여 LINQ to Objects 쿼리의 실행 속도를 높이는 데 있습니다.  PLINQ는 개별 대리자 간에 상태가 공유되지 않고 소스 컬렉션의 각 요소에 대한 처리가 독립적으로 수행될 때 가장 뛰어난 성능을 제공합니다.  이러한 병렬 연산은 LINQ to Objects 및 PLINQ에서는 일반적인 것입니다. 또한 다중 스레드에서 쉽게 예약할 수 있기 때문에 종종 "*매우 만족스러운 병렬*"이라고 불리기도 합니다.  그러나 모든 쿼리가 이러한 병렬 연산으로만 구성되는 것은 아닙니다. 대부분의 경우 쿼리에는 병렬화할 수 없거나 병렬 실행의 속도를 감소시키는 연산자가 일부 포함됩니다.  쿼리가 완전히 만족스러운 수준으로 병렬화되어 있는 경우에도 PLINQ에서는 데이터 소스를 분할하고 스레드의 작업을 예약해야 하며 쿼리 완료 시 결과를 병합해야 합니다.  이러한 연산은 모두 병렬화의 계산 비용을 증가시킵니다. 이와 같이 병렬화 추가에 따르는 비용을 *오버헤드*라고 합니다.  PLINQ 쿼리에서 성능을 최적화하려면 매우 만족스럽게 병렬화되어 있는 파트를 극대화하고 오버헤드를 유발하는 파트를 최소화해야 합니다.  이 문서에서는 최대한 효율적이면서 정확한 결과를 산출하는 PLINQ 쿼리를 작성하는 데 도움이 되는 정보를 제공합니다.  
  
## PLINQ 쿼리 성능에 영향을 주는 요인  
 다음 단원에서는 병렬 쿼리 성능에 영향을 미치는 가장 중요한 일부 요인에 대해 설명합니다.  이러한 설명은 일반적 수준에서 제공되므로 모든 경우의 쿼리 성능을 예측하는 데는 충분치 않습니다.  따라서 항상 그렇듯이 대표적인 구성 및 부하의 범위 내에서 특정 쿼리를 컴퓨터에서 실행하여 실제 성능을 측정해야 합니다.  
  
1.  전체 작업의 계산 비용.  
  
     속도를 향상시키려면 PLINQ 쿼리에 포함된 작업이 오버헤드를 상쇄할 정도의 높은 수준으로 병렬화되어 있어야 합니다.  작업은 각 대리자의 계산 비용에 소스 컬렉션의 요소 수를 곱한 값으로 나타낼 수 있습니다.  연산이 병렬화될 수 있으면 계산 비용이 증가할수록 속도 향상의 가능성이 늘어납니다.  예를 들어, 함수 실행에 소요되는 시간이 1밀리초인 경우 1000개의 요소에 대한 순차적 쿼리로 해당 연산을 수행하려면 1초가 걸립니다. 이에 비해 코어가 4개인 컴퓨터에서 병렬 쿼리를 사용하면 250밀리초만 소요됩니다.  즉, 750밀리초만큼 속도가 향상됩니다.  이 함수가 각 요소에 대해 실행되는 데 1초가 필요하다면 속도는 750초나 향상됩니다.  대리자의 부담이 매우 큰 경우 PLINQ에서는 소스 컬렉션의 일부 항목만 사용하여 속도를 크게 향상시킬 수 있습니다.  반대로, 대리자의 부담이 적고 크기가 작은 소스 컬렉션은 일반적으로 PLINQ에 적합하지 않습니다.  
  
     다음 예제에서 Select 함수가 많은 작업을 수행한다고 가정할 경우 queryA는 아마 PLINQ의 좋은 후보입니다. queryB는 Select 문에서의 작업이 부족하기 때문에 아마 좋은 후보가 아닐 것이고, 병렬 처리의 오버 헤드가 대부분의 속도 증가를 오프셋 할 것입니다.  
  
    ```vb  
    Dim queryA = From num In numberList.AsParallel()  
                 Select ExpensiveFunction(num); 'good for PLINQ  
  
    Dim queryB = From num In numberList.AsParallel()  
                 Where num Mod 2 > 0  
                 Select num; 'not as good for PLINQ  
    ```  
  
    ```csharp  
    var queryA = from num in numberList.AsParallel()  
                 select ExpensiveFunction(num); //good for PLINQ  
  
    var queryB = from num in numberList.AsParallel()  
                 where num % 2 > 0  
                 select num; //not as good for PLINQ  
  
    ```  
  
2.  시스템의 논리 코어 수\(병렬화 수준\).  
  
     이 요인은 이전 단원으로부터 필연적으로 유도됩니다. 코어가 많은 컴퓨터에서는 작업이 더 많은 동시 스레드 간에 분할될 수 있기 때문에 매우 높은 수준으로 병렬화되어 있는 쿼리는 더 빠르게 실행됩니다.  쿼리에 포함된 전체 작업 중 어느 정도를 병렬화할 수 있는지에 따라 전반적인 속도 향상의 폭이 결정됩니다.  그러나 코어가 4개인 컴퓨터에 비해 코어가 8개인 컴퓨터에서 모든 쿼리가 2배 빠르게 실행된다고 가정하면 안 됩니다.  최적 성능을 위해 쿼리를 튜닝할 경우 코어 수가 서로 다른 여러 컴퓨터에서 실제 결과를 측정해야 합니다.  이 요인은 첫 번째 요인과 관련되어 있습니다. 데이터 집합의 규모가 클수록 더 많은 계산 리소스를 활용해야 하기 때문입니다.  
  
3.  연산의 수 및 종류.  
  
     PLINQ에서는 소스 시퀀스의 요소 순서를 유지해야 하는 경우에 사용 가능한 AsOrdered 연산자를 제공합니다.  정렬과 관련하여 발생하는 비용도 있지만 이 비용은 일반적으로 별로 크지 않습니다.  GroupBy 및 Join 연산 역시 오버헤드를 유발합니다.  PLINQ는 소스 컬렉션의 요소를 임의 순서로 처리하고 요소가 준비되는 즉시 다음 연산자로 요소를 전달할 수 있을 때 최상의 성능을 제공합니다.  자세한 내용은 [Order Preservation in PLINQ](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)을 참조하십시오.  
  
4.  쿼리 실행 형태.  
  
     ToArray 또는 ToList를 호출하여 쿼리 결과를 저장할 경우 모든 병렬 스레드의 결과는 단일 데이터 구조에 병합되어야 합니다.  이에 따라 계산 비용이 발생하는 것은 필연적입니다.  마찬가지로, foreach\(Visual Basic에서는 For Each\) 루프를 사용하여 결과를 반복하는 경우 작업자 스레드의 결과는 열거자 스레드에서 serialize되어야 합니다.  그러나 각 스레드의 결과에 기반하여 일부 작업만 수행하려는 경우에는 ForAll 메서드를 사용하여 다중 스레드에서 해당 작업을 수행할 수 있습니다.  
  
5.  병합 옵션 유형.  
  
     PLINQ는 출력을 버퍼링하여 청크 방식으로 생성하거나 전체 결과 집합이 생성된 후 한 번에 모두 생성하도록 구성하거나, 개별 결과가 생성되는 대로 스트림하도록 구성할 수 있습니다.  첫 번째 구성 방식에 따르면 전반적인 실행 시간이 줄어들고, 두 번째 구성 방식에 따르면 생성되는 요소 사이의 지연이 감소합니다.  병합 옵션이 전반적인 쿼리 성능에 대해 항상 중요한 영향을 미치는 것은 아니지만 사용자가 결과를 확인하기 위해 기다려야 하는 시간을 제어하기 때문에 사용자가 체감하는 성능에는 영향을 미칠 수 있습니다.  자세한 내용은 [Merge Options in PLINQ](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)을 참조하십시오.  
  
6.  분할의 종류.  
  
     경우에 따라서는 인덱싱 가능한 소스 컬렉션에 대한 PLINQ 쿼리로 인해 작업 부하가 균일하지 않게 될 수도 있습니다.  이러한 경우에는 사용자 지정 파티셔너를 만들어 쿼리 성능을 증가시킬 수 있습니다.  자세한 내용은 [Custom Partitioners for PLINQ and TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)을 참조하십시오.  
  
## PLINQ에서 순차 모드가 선택되는 경우  
 PLINQ에서는 최소한 쿼리가 순차적으로 실행될 때만큼의 속도로 쿼리를 실행하려고 항상 시도합니다.  PLINQ에서는 사용자 대리자의 계산 부담이 어느 정도인지 또는 입력 소스의 크기가 어느 정도인지 확인하지 않지만 특정 쿼리의 "형태"는 살펴봅니다. 특히, 병렬 모드에서 쿼리 실행 속도를 더욱 낮추는 쿼리 연산자 또는 연산자 조합을 찾아냅니다.  쿼리에서 이러한 형태가 발견되면 PLINQ는 기본적으로 순차 모드로 전환됩니다.  
  
 그러나 특정 쿼리의 성능을 측정한 후에는 해당 쿼리가 병렬 모드에서 실제로 더 빠르게 실행되는지 확인할 수 있습니다.  이러한 경우 <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A?displayProperty=fullName> 메서드를 통해 <xref:System.Linq.ParallelExecutionMode> 플래그를 사용하여 PLINQ에게 해당 쿼리를 병렬화하도록 지시할 수 있습니다.  자세한 내용은 [How to: Specify the Execution Mode in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)을 참조하십시오.  
  
 다음 목록에서는 PLINQ가 기본적으로 순차 모드로 실행하는 쿼리 형태에 대해 설명합니다.  
  
-   원래 인덱스를 제거하거나 다시 정렬한 필터링 또는 정렬 연산자 뒤에 있는 Select, 인덱싱된 Where, 인덱싱된 SelectMany, 또는 ElementAt 절을 포함하는 쿼리  
  
-   Take, TakeWhile, Skip, SkipWhile 연산자를 포함하고 소스 시퀀스의 인덱스가 원래 순서와 다른 쿼리  
  
-   데이터 소스 중 하나에서 원래 순서대로 인덱스가 유지되거나 다른 데이터 소스가 인덱싱 가능한 \(예. 배열 또는 IList\(T\)\) 경우가 아닌 경우의 Zip 또는 SequenceEquals를 포함하는 쿼리  
  
-   Concat을 포함하는 쿼리. 인덱싱 가능한 데이터 소스에 적용되지 않는 경우  
  
-   Reverse를 포함하는 쿼리. 인덱싱 가능한 데이터 소스에 적용되지 않는 경우  
  
## 참고 항목  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)