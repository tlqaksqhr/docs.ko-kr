---
title: SpinLock
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7d1d95030d2bc9f9288ae134471c150a37291b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582261"
---
# <a name="spinlock"></a>SpinLock
<xref:System.Threading.SpinLock> 구조는 잠금을 획득하기 위해 대기하는 동안 회전하는 하위 수준의 동기화 기본 형식입니다. 멀티 코어 컴퓨터에서 대기 시간이 짧은 것으로 예상되고 경합이 최소인 경우 <xref:System.Threading.SpinLock>의 성능이 다른 종류의 잠금보다 더 뛰어납니다. 그러나 프로파일링을 통해 <xref:System.Threading.Monitor?displayProperty=nameWithType> 메서드 또는 <xref:System.Threading.Interlocked> 메서드가 프로그램의 성능을 크게 낮추는 것을 확인하는 경우에만 <xref:System.Threading.SpinLock>을 사용하는 것이 좋습니다.  
  
 <xref:System.Threading.SpinLock>은 아직 잠금을 획득하지 않은 경우에도 스레드의 시간 조각을 생성할 수 있습니다. 스레드 우선 순위가 반전되는 것을 방지하고 가비지 수집기가 진행되도록 하기 위해 이 작업을 수행합니다. <xref:System.Threading.SpinLock>을 사용하면 스레드가 매우 짧은 시간 범위 이상으로 잠금을 보유할 수 없고 잠금을 보유하는 동안 스레드가 차단할 수 없습니다.  
  
 SpinLock은 값 형식이므로 두 개의 사본이 동일한 잠금을 참조하도록 하려는 경우 참조를 통해 명시적으로 전달해야 합니다.  
  
 이 유형을 사용하는 방법에 대한 자세한 내용은 <xref:System.Threading.SpinLock?displayProperty=nameWithType>을 참조하세요. 예를 들어 [방법: 낮은 수준의 동기화에 SpinLock 사용](../../../docs/standard/threading/how-to-use-spinlock-for-low-level-synchronization.md)을 참조하세요.  
  
 <xref:System.Threading.SpinLock>은 ‘스레드 추적’ 모드를 지원합니다. 스레드 추적 모드는 특정 시간에 잠금을 보유하고 있는 스레드를 추적하기 위해 개발 단계 중에 사용할 수 있습니다.- 스레드 추적 모드는 디버깅에 매우 유용하지만 성능이 저하될 수 있으므로 프로그램의 릴리스 버전에서 끄는 것이 좋습니다. 자세한 내용은 [방법: 회전 잠금에서 스레드 추적 모드 사용](../../../docs/standard/threading/how-to-enable-thread-tracking-mode-in-spinlock.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)
