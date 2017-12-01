---
title: "방법: 스핀 잠금에서 스레드-추적 모드 사용"
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>방법: 스핀 잠금에서 스레드-추적 모드 사용
<xref:System.Threading.SpinLock?displayProperty=nameWithType>낮은 수준의 상호 배제 하는 매우 짧은 대기 시간이 없는 시나리오에 사용할 수 있습니다. <xref:System.Threading.SpinLock>재진입 성이 아닙니다. 스레드가 이미 잠금을 획득을 종료 해야 잠금을 잘못 다시 시작할 수 있으려면 먼저 합니다. 일반적으로 잠금을 다시 시작 하려는 시도 인해 교착 상태를 하 고 교착 상태 디버깅이 어려워질 수 있습니다. 개발, 높이기 위해 <xref:System.Threading.SpinLock?displayProperty=nameWithType> 스레드가 이미 획득 한 잠금을 다시 입력 하려고 할 때 throw 되는 예외를 발생 시킨 스레드-추적 모드를 지원 합니다. 이는 잠금을 올바르게 종료 되지 않은 지점 보다 쉽게 찾을 수 있습니다. 스레드-추적 모드를 사용 하 여 켤 수 있습니다는 <xref:System.Threading.SpinLock> 부울 값을 사용 하는 생성자의 인수에 전달 하 고 매개 변수를 입력 `true`합니다. 개발 및 테스트 단계를 완료 한 후 성능 향상을 위해 스레드-추적 모드를 해제 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 스레드-추적 모드를 보여 줍니다. 올바르게 잠금을 종료 하는 줄은 다음 결과 중 하나를 발생 시키는 코딩 오류를 시뮬레이션 하 주석 처리 됩니다.  
  
-   예외가 발생 하는 경우는 <xref:System.Threading.SpinLock> 의 인수를 사용 하 여 만든 `true` (`True` Visual basic에서).  
  
-   경우 교착 상태는 <xref:System.Threading.SpinLock> 의 인수를 사용 하 여 만든 `false` (`False` Visual basic에서).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>참고 항목  
 [스핀 잠금](../../../docs/standard/threading/spinlock.md)
