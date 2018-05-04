---
title: .NET으로 병렬 프로그래밍
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
helpviewer_keywords:
- parallel programming
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 679ffe40e525884070ee62662b7a7e5acd7e58ad
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="parallel-programming-in-net"></a>.NET으로 병렬 프로그래밍

여러 개인용 컴퓨터 및 워크스테이션에는 여러 CPU 코어가 있기 때문에 다중 스레드가 동시에 실행될 수 있습니다. 가까운 미래에 컴퓨터의 코어 수는 대폭 증가할 것으로 예상됩니다. 현재 및 미래의 하드웨어를 활용하기 위해 코드를 병렬화하여 작업을 여러 프로세스에 분산할 수 있습니다. 이전의 병렬화에서는 스레드 및 잠금에 대한 저수준 조작이 필요했습니다. Visual Studio 2010 및 .NET Framework 4에서는 새로운 런타임, 새로운 클래스 라이브러리 형식 및 새로운 진단 도구를 제공하여 병렬 프로그래밍에 대한 지원이 향상되었습니다. 이러한 기능은 병렬 개발을 단순화하기 때문에 개발자는 스레드 또는 스레드 풀을 직접 건드릴 필요 없이 효율적이고 세부적이고 확장명 가능한 병렬 코드를 자연스러운 언어로 작성할 수 있습니다. 다음 그림에서는 .NET Framework 4의 병렬 프로그래밍 아키텍처에 대한 간략한 개요를 제공합니다.
  
 ![.NET 병렬 프로그래밍 아키텍처](./media/tpl-architecture.png "TPL_Architecture")  
  
## <a name="related-topics"></a>관련 항목  
  
|기술|설명|  
|----------------|-----------------|  
|[TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|<xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> 및 `For` 루프의 병렬 버전을 포함하는 `ForEach` 클래스 및 비동기 작업에 대한 선호되는 표현 방식을 나타내는 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 클래스의 설명서를 제공합니다.|  
|[PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|여러 시나리오에서 성능을 대폭 향상시키는 LINQ to Objects의 병렬 구현입니다.|  
|[병렬 프로그래밍을 위한 데이터 구조](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|스레드로부터 안전한 컬렉션 클래스, 간단한 동기화 형식 및 초기화 지연 관련 형식에 대한 설명서의 링크를 제공합니다.|  
|[병렬 진단 도구](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Visual Studio 디버거의 작업 및 병렬 스택 창에 대한 설명서와 병렬 코드의 디버깅 및 성능 튜닝에 사용 가능한 [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] 프로파일러의 뷰 집합으로 구성되는 [Concurrency Visualizer](/visualstudio/profiling/concurrency-visualizer)에 대한 설명서의 링크를 제공합니다.|  
|[PLINQ 및 TPL에 대한 사용자 지정 파티셔너](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|파티션 작동 방식 및 기본 파티션을 구성하거나 새 파티션을 만드는 방법에 대해 설명합니다.|  
|[작업 스케줄러](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|스케줄러 작동 방식 및 기본 스케줄러의 구성 방법에 대해 설명합니다.|  
|[PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|C# 및 Visual Basic으로 작성된 람다 식의 간략한 개요를 제공하고, 람다 식이 PLINQ 및 작업 병렬 라이브러리에서 사용되는 방식을 보여 줍니다.|  
|[추가 정보](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|.NET의 병렬 프로그래밍과 관련된 추가 정보 및 샘플 리소스에 대한 링크를 제공합니다.|  

## <a name="see-also"></a>참고 항목  
 [비동기 개요](../async.md)  
 [관리되는 스레딩](../threading/index.md)  
