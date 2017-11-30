---
title: "PLINQ의 속도 향상 이해"
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
helpviewer_keywords: PLINQ queries, performance tuning
ms.assetid: 53706c7e-397d-467a-98cd-c0d1fd63ba5e
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3373cb6a2c535bd7d42eb062e1f9727952f7cfb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="understanding-speedup-in-plinq"></a>PLINQ의 속도 향상 이해
PLINQ의 주 목적은 다중 코어 컴퓨터에서 병렬로 쿼리 대리자를 실행 하 여 개체 쿼리는 LINQ의 실행을 가속화 하는 것입니다. PLINQ는 소스 컬렉션에 있는 각 요소의 처리는 독립적 이며 사용할 수 있는 공유 상태 간에 개별 대리자 때 가장 잘 수행 합니다. 이러한 작업은 LINQ to Objects 및 PLINQ에서에서 일반적으로 되 고 통칭 되 "*이러한 병렬*" 것에 중점을 두 쉽게 여러 스레드를 예약 하기 때문에 있습니다. 그러나 모든 쿼리에 이러한 병렬 작업 대부분의 경우 쿼리 하나 평행 화할 수 없는, 또는 병렬 실행 속도가 저하 하는 몇 가지 연산자를 통해 합니다. 와 완전히 병렬화 되어 있는 쿼리를 PLINQ 해야 데이터 소스를 분할 하 고 작업을 스레드를 예약 하며 쿼리가 완료 되 면 결과 병합 합니다. 이 작업은 모두 병렬화;의 계산 비용에 추가 병렬 처리 기능을 추가 하는 이러한 비용 라고 *오버 헤드*합니다. PLINQ 쿼리의 성능을 최적화 하려면, 목표 병렬화 되어 있는 파트를 최대화 하 고 오버 헤드를 필요로 하는 파트를 최소화 하는 것입니다. 이 문서는 올바른 결과 산출 하는 동안 최대한 효율적으로 PLINQ 쿼리를 작성 하는 데 도움이 되는 정보를 제공 합니다.  
  
## <a name="factors-that-impact-plinq-query-performance"></a>PLINQ 쿼리 성능에 영향을 주는 요소  
 다음 섹션에서는 병렬 쿼리 성능에 영향을 해당 가장 중요 한 요소 중 일부를 보여 줍니다. 이 일반 문 자체 만으로는 부족 한 모든 경우에에서 쿼리 성능을 예측할 수입니다. 늘 그렇듯이 대표 구성 및 부하의 범위를 컴퓨터에 대 한 특정 쿼리의 실제 성능을 측정을 고려해 야 합니다.  
  
1.  전체 작업의 계산 비용입니다.  
  
     PLINQ 쿼리 속도 향상 시키려면 오버 헤드를 충분 한 이러한 병렬 작업이 있어야 합니다. 작업의 소스 컬렉션의 요소 수를 곱한 각 대리자의 계산 비용으로 표현할 수 있습니다. 가정 하는 작업 병렬화 될 수 있으면 계산 비용이 많이 드는 인 큼 속도 대 한 기회입니다. 예를 들어, 함수가 실행에 1 밀리초를 사용 하는 경우 1000 요소 걸립니다 해당 작업을 수행 하려면 1 초 4 개의 코어를 사용 하는 컴퓨터에서 병렬 쿼리 하는 반면 순차적 쿼리 초가 걸릴 수 있습니다. 750 밀리초의 속도 생성합니다. 함수가 각 요소에 대해 실행할 수는 1 초, 필요한 경우 지금까지 750 초 것 다음입니다. 대리자가 부담이, PLINQ 소스 컬렉션의 항목 수가 적은와 중요 한 속도 향상을 제공할 수 있습니다. 반대로 크기가 작은 소스 trivial 대리자 컬렉션은 일반적으로 적합 하지 않습니다 PLINQ에 대 한 합니다.  
  
     다음 예에서 queryA 때문일에 적합 한 많은 작업 함수는 선택 과정이 포함 되어 있음을 가정 PLINQ 수 있습니다. queryB Select 문에서 충분 한 작업이 없기 때문에는 병렬화 오버 헤드 대부분 또는 지금까지 모두 만큼 오프셋 됩니다 적합 없는 것입니다.  
  
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
  
2.  시스템 (병렬 처리 수준)의 논리 코어 수입니다.  
  
     이 점은 이전 섹션에는 확실 한 단독, 병렬화 되어 있는 쿼리 실행 속도가 컴퓨터에서 더 많은 코어와 더 많은 동시 스레드 간에 작업을 구분할 수 있습니다. 전반적인 속도의 양이 병렬화 된 쿼리의 전체 작업의 비율에 따라 달라 집니다. 그러나 가정 하지 마십시오 모든 쿼리도 두 번 실행 됩니다 4 코어 컴퓨터와는 8 개 코어 컴퓨터에서 빠른 합니다. 최적의 성능을 위해 쿼리를 튜닝 하는 경우에 다양 한 수의 코어 시스템에 실제 결과 측정 해야 합니다. 이 지점 관련 되어 #1: 더 큰 컴퓨팅 리소스를 활용 하는 데 필요한 데이터 집합이 큰 경우.  
  
3.  작업의 종류와 수 있습니다.  
  
     PLINQ는 소스 시퀀스에서 요소의 순서를 유지 해야 하는 상황을 위한 AsOrdered 연산자를 제공 합니다. 순서와 관련 된 비용이 발생 하지만이 비용은 속도가 일반적으로 빠릅니다. 마찬가지로 GroupBy 및 조인 작업 해야 오버 헤드가 발생 합니다. PLINQ를 순서에 관계 없이 소스 컬렉션의 요소를 처리 하 고 다음 운영자에 게 전달 하는 업데이트가 준비 되는 즉시 허용 될 때 최적으로 수행 합니다. 자세한 내용은 [PLINQ에서 순서 유지](../../../docs/standard/parallel-programming/order-preservation-in-plinq.md)를 참조하세요.  
  
4.  쿼리 실행의 형식입니다.  
  
     ToArray 또는 ToList 호출 하 여 쿼리의 결과 저장 하는 경우 단일 데이터 구조에는 모든 병렬 스레드의 결과를 병합 해야 합니다. 이 불가피 한 계산 비용을 해야합니다. 마찬가지로, (각각에 대해 Visual basic에서) foreach 루프를 사용 하 여 결과 반복 하는 경우 작업자 스레드의 결과를 열거자 스레드 serialize 할 수 있어야 합니다. 하지만 각 스레드에서 결과에 따라 일부 작업을 수행 하려면 여러 스레드에서이 작업을 수행 하는 ForAll 메서드를 사용할 수 있습니다.  
  
5.  병합 옵션의 형식입니다.  
  
     PLINQ 하거나 해당 출력을 버퍼링 하 고 전체 결과 집합이 생성 되 또는 else 스트림 개별 결과를 생성 된 후 또는 한 번에 청크에서 생성 하도록 구성할 수 있습니다. 이전 결과는 구성된 요소 간의 지연이 감소 후자 결과 및 전반적인 실행 시간이입니다.  병합 옵션 항상 없는 반면 큰 영향을 전체 쿼리 성능에,은 영향을 줄 수 인식된 성능을 기간 사용자를 제어 하기 때문에 결과를 볼 때까지 대기 해야 합니다. 자세한 내용은 [PLINQ의 병합 옵션](../../../docs/standard/parallel-programming/merge-options-in-plinq.md)을 참조하세요.  
  
6.  분할의 종류입니다.  
  
     일부 경우에 인덱싱 가능한 소스 컬렉션에 대해 PLINQ 쿼리 불균형된 작업 로드 될 수 있습니다. 이 경우 사용자 지정 파티 셔 너를 만들어 쿼리 성능을 향상 시킬 수 있습니다. 자세한 내용은 [PLINQ 및 TPL에 대한 사용자 지정 파티셔너](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)를 참조하세요.  
  
## <a name="when-plinq-chooses-sequential-mode"></a>PLINQ 순차 모드를 선택 하는 경우  
 PLINQ는 항상 빠른 쿼리 순차적으로 실행 되는 쿼리를 실행 하려고 합니다. PLINQ에서 검사 하지 않습니다 방법을. 계산 되지만 비용이 많이 드는 사용자 대리자, 이거나 얼마나 큰 입력된 소스, "shapes" 특정 쿼리에 대 한 확인지 않습니다. 특히 쿼리 연산자 또는 병렬 모드에서 느리게 실행 쿼리 연산자의 조합을 찾습니다. 이러한 셰이프를 발견 하면 기본적으로 plinq가 순차 모드입니다.  
  
 그러나 특정 쿼리 성능을 측정 하므로 후 실제로 실행 더 빠르게 병렬 모드에서 결정할 수 있습니다. 이러한 경우에 사용할 수 있습니다는 <xref:System.Linq.ParallelExecutionMode.ForceParallelism?displayProperty=nameWithType> 통해 플래그는 <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> 메서드를 plinq에서 쿼리를 병렬화 하도록 합니다. 자세한 내용은 [방법: PLINQ에 실행 모드 지정](../../../docs/standard/parallel-programming/how-to-specify-the-execution-mode-in-plinq.md)을 참조하세요.  
  
 다음 목록에서는 기본적으로 PLINQ 순차 모드에서 실행 되는 쿼리 형태를 설명 합니다.  
  
-   Select를 포함 하는 쿼리 인덱싱된 인덱싱된 SelectMany Where, 또는 이후를 제거 하거나 원래 인덱스를 다시 정렬 하지 않은 순서 지정 또는 필터링 연산자 ElementAt 절.  
  
-   TakeWhile, Take, Skip, SkipWhile 연산자를 포함 하 고 소스 시퀀스에서 인덱스가 없는 원래 순서로 쿼리 합니다.  
  
-   Zip 또는 SequenceEquals를 포함하는 쿼리. 데이터 소스 중 하나에서 원래 순서대로 인덱스가 유지되고 다른 데이터 소스는 인덱싱 가능한 배열 또는 IList(T)가 아닌 경우  
  
-   인덱싱 가능 데이터 원본에 적용 하지 않는 한 Concat를 포함 하는 쿼리.  
  
-   인덱싱 가능 데이터 원본에 적용 하지 않는 한 반대의 경우를 포함 하는 쿼리.  
  
## <a name="see-also"></a>참고 항목  
 [PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
