---
title: ".NET Framework의 병렬 프로그래밍 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: c50b3e328998b65ec47efe6d7457b36116813c77
ms.openlocfilehash: 6a163776f358691c0f61c90dce98c15bebe4052a
ms.lasthandoff: 04/08/2017

---
# <a name="parallel-programming-in-the-net-framework"></a>.NET Framework의 병렬 프로그래밍
여러 개인용 컴퓨터 및 워크스테이션에는 코어, 즉 CPU가 2개 또는 4개 있기 때문에 다중 스레드가 동시에 실행될 수 있습니다. 가까운 미래에 컴퓨터의 코어 수는 대폭 증가할 것으로 예상됩니다. 현재 및 미래의 하드웨어를 활용하기 위해 코드를 병렬화하여 작업을 여러 프로세스에 분산할 수 있습니다. 이전의 병렬화에서는 스레드 및 잠금에 대한 저수준 조작이 필요했습니다. [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] 및 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 새로운 런타임, 새로운 클래스 라이브러리 형식 및 새로운 진단 도구를 제공하여 병렬 프로그래밍에 대한 지원이 향상되었습니다. 이러한 기능은 병렬 개발을 단순화하기 때문에 개발자는 스레드 또는 스레드 풀을 직접 건드릴 필요 없이 효율적이고 세부적이고 확장명 가능한 병렬 코드를 자연스러운 언어로 작성할 수 있습니다. 다음 그림에서는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]의 병렬 프로그래밍 아키텍처에 대한 간략한 개요를 제공합니다.  
  
 ![.NET 병렬 프로그래밍 아키텍처](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL_Architecture")  
  
## <a name="related-topics"></a>관련 항목  
  
|기술|설명|  
|----------------|-----------------|  
|[TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|`For` 및 `ForEach` 루프의 병렬 버전을 포함하는 <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> 클래스 및 비동기 작업을 표현하는 기본 방법을 나타내는 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스에 대한 설명서를 제공합니다.|  
|[PLINQ(병렬 LINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|여러 시나리오에서 성능을 대폭 향상시키는 LINQ to Objects의 병렬 구현입니다.|  
|[병렬 프로그래밍을 위한 데이터 구조](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|스레드로부터 안전한 컬렉션 클래스, 간단한 동기화 형식 및 초기화 지연 관련 형식에 대한 설명서의 링크를 제공합니다.|  
|[병렬 진단 도구](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Visual Studio 디버거의 작업 및 병렬 스택 창에 대한 설명서와 병렬 코드의 디버깅 및 성능 튜닝에 사용 가능한 [!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)] 프로파일러의 뷰 집합으로 구성되는 [Concurrency Visualizer](http://msdn.microsoft.com/library/ae5879a0-1e1a-455a-ba72-148e57f59289)에 대한 설명서의 링크를 제공합니다.|  
|[PLINQ 및 TPL에 대한 사용자 지정 파티셔너](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|파티션 작동 방식 및 기본 파티션을 구성하거나 새 파티션을 만드는 방법에 대해 설명합니다.|  
|[작업 스케줄러](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|스케줄러 작동 방식 및 기본 스케줄러의 구성 방법에 대해 설명합니다.|  
|[PLINQ 및 TPL의 람다 식](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|C# 및 Visual Basic으로 작성된 람다 식의 간략한 개요를 제공하고, 람다 식이 PLINQ 및 작업 병렬 라이브러리에서 사용되는 방식을 보여 줍니다.|  
|[추가 정보](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|.NET Framework의 병렬 프로그래밍과 관련된 추가적 설명서 및 샘플 리소스에 대한 링크를 제공합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [병렬 프로그래밍 패턴: .NET Framework 4의 병렬 패턴 이해 및 적용](http://go.microsoft.com/fwlink/?LinkID=185142)   
 [NET Framework를 사용한 병렬 프로그래밍 샘플](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
