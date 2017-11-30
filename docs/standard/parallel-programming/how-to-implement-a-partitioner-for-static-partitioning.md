---
title: "방법: 정적 분할을 위한 파티셔너 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: tasks, how to create a static partitioner
ms.assetid: f4410508-cac6-4ba7-bef1-c5e68b2794f3
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b28ff0bb8436fefc4956918889435e258ae98b12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-implement-a-partitioner-for-static-partitioning"></a>방법: 정적 분할을 위한 파티셔너 구현
다음 예제에서는 정적 분할을 수행 하는 PLINQ에 대 한 간단한 사용자 지정 파티 셔를 구현 하는 방법을 보여 줍니다. 사용 될 없는 파티 셔 너 동적 파티션을 지원 하지 않으므로, <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>합니다. 이 파티 셔 각 요소에 많은 양의 처리 시간이 필요를 데이터 원본에 대 한 파티 셔 너는 기본 범위를 통해 빠른 속도 제공 합니다.  
  
## <a name="example"></a>예제  
 [!code-csharp[TPL_Partitioners#05](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_partitioners/cs/partitioners.cs#05)]  
  
 이 예에서 파티션 각 요소에 대 한 처리 시간이 증가 하는 선형의 가정을 기반으로 합니다. 실제 상황에서이 방식으로 처리 시간을 예측 하기 어려울 수 있습니다. 정적 파티 셔 너의 특정 데이터 원본을 사용 하는 경우 있습니다 수 최적화 소스에 대 한 분할 수식, 부하 분산 논리를 추가 또는 청크에서와 같이 분할 방법을 사용 하 여 [하는 방법: 동적 파티션 구현](../../../docs/standard/parallel-programming/how-to-implement-dynamic-partitions.md).  
  
## <a name="see-also"></a>참고 항목  
 [PLINQ 및 TPL에 대한 사용자 지정 파티셔너](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)
