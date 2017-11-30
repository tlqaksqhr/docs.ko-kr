---
title: "방법: 동시 작업을 배리어와 동기화"
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
helpviewer_keywords: Barrier, how to use
ms.assetid: e1a253ff-e0fb-4df8-95ff-d01a90d4cb19
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0b2e32fe3cec30a4da7467447aee625dfe7e379b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-synchronize-concurrent-operations-with-a-barrier"></a>방법: 동시 작업을 배리어와 동기화
다음 예제에서는 동시 작업을 동기화 하는 <xref:System.Threading.Barrier>합니다.  
  
## <a name="example"></a>예제  
 다음 프로그램의 목적은 개수 반복 (또는 단계)를 계산 하 스레드를 각 찾기 두 개에 대 한 솔루션의 절반 동일한 단계에서 사용 하 여 필요한 섞은 알고리즘으로 단어입니다. 각 스레드는 해당 단어 섞은 후, 후 장벽 사후 단계 작업 전체 문장 올바른 단어 순서 대로 렌더링 된 경우를 확인 하려면 두 개의 결과 비교 합니다.  
  
 [!code-csharp[CDS_Barrier#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#01)]
 [!code-vb[CDS_Barrier#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#01)]  
  
 A <xref:System.Threading.Barrier> 는 모든 작업 장벽에 도달할 때까지 계속에서 병렬 작업에서 개별 작업을 방지 하는 개체입니다. 병렬 작업 단계에서 발생 하 고 각 단계는 작업 간의 동기화를 필요로 하는 경우에 유용 합니다. 이 예제에서는 작업에는 방법은 두 단계가 있습니다. 첫 번째 단계에서 각 작업은 데이터를 사용 하 여 버퍼의 항목을 채웁니다. 각 작업 항목을 채우는 완료 되 면 작업을 계속 하려면 준비 된 장벽 및 대기를 알립니다. 모든 작업이 장벽 신호를 받을 때에 차단 해제 되 고 두 번째 단계를 시작 합니다. 장벽은 두 번째 단계를 사용 하려면 각 작업 있어야이 지점에 생성 된 모든 데이터에 액세스할 필요 합니다. 장벽이 없으면 첫 번째 작업이 완료 되지 채워 졌을 아직 다른 작업에서 버퍼에서 읽을 하려고 할 수 있습니다. 이런이 방식으로 단계 개수에 관계 없이 동기화 할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [병렬 프로그래밍을 위한 데이터 구조](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)
