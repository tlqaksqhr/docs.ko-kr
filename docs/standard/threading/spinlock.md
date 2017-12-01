---
title: SpinLock
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: efe9b3126b3c952ab156f9ca40752ad8d3fddcd1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="spinlock"></a>SpinLock
<xref:System.Threading.SpinLock> 구조는 하위 수준, 상호 배제 동기화 기본 형식 잠금을 획득 하려고 대기 하는 동안 회전 합니다. 대기 시간이 짧은 하 고 경합은 최소화 되도록 예상 되는 경우 다중 코어 컴퓨터에서 <xref:System.Threading.SpinLock> 다른 종류의 잠금 보다 더 나은 수행할 수 있습니다. 하지만 사용 하는 권장 <xref:System.Threading.SpinLock> 프로 파일링을 통해 결정할 때만 <xref:System.Threading.Monitor?displayProperty=nameWithType> 메서드 또는 <xref:System.Threading.Interlocked> 메서드는 프로그램의 성능이 느려질 수 있으므로 크게 합니다.  
  
 <xref:System.Threading.SpinLock>잠금을 획득 아직 하지 하는 경우에 스레드 시간 간격을 얻을 수도 있습니다. 스레드 우선 순위 inversion 방지 하 고 작업을 진행 하기 위해 가비지 수집기를 사용 하도록 설정 하려면이 수행 합니다. 사용 하는 경우는 <xref:System.Threading.SpinLock>, 스레드가 없습니다 매우 짧은 기간 보다 그 이상는 잠금을 보유할 수 있는지 확인 하 잠금을 유지 하는 동안 스레드가 없습니다 차단할 수 있습니다.  
  
 SpinLock 값 형식이 때문에 명시적으로 전달 해야 참조로 동일한 잠금을를 가리키는 두 복사본을 가져오려는 경우.  
  
 이 유형을 사용 하는 방법에 대 한 자세한 내용은 참조 <xref:System.Threading.SpinLock?displayProperty=nameWithType>합니다. 예를 들어 참조 [하는 방법: 하위 수준 동기화에 SpinLock 사용](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)합니다.  
  
 <xref:System.Threading.SpinLock>지원는 *스레드*-*추적* 특정 시간에는 잠금을 보유 하는 스레드를 추적 하려면 개발 단계에서 사용할 수 있는 모드입니다. 스레드-추적 모드는 디버깅에 매우 유용 하지만 해제 하는 해당 프로그램의 릴리스 버전에서 성능 저하 시킬 수 있으므로 하는 것이 좋습니다. 자세한 내용은 참조 [하는 방법: 스레드를 사용 하도록 설정-추적 모드 SpinLock](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
