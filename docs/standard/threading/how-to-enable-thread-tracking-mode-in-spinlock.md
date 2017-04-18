---
title: "How to: Enable Thread-Tracking Mode in SpinLock | Microsoft Docs"
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
  - "SpinLock, how to enable thread-tracking"
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Enable Thread-Tracking Mode in SpinLock
<xref:System.Threading.SpinLock?displayProperty=fullName>은 대기 시간이 매우 짧은 시나리오에서 사용할 수 있는 하위 수준 상호 제외 잠금입니다.  <xref:System.Threading.SpinLock>은 다시 시작할 수 없습니다.  스레드가 이미 획득된 잠금을 다시 잠그려면 먼저 잠금을 올바르게 종료해야 합니다.  일반적으로 이미 획득된 잠금을 다시 잠그려고 하면 디버깅하기 매우 어려울 수 있는 교착 상태가 발생할 수 있습니다.  개발 단계를 위해 <xref:System.Threading.SpinLock?displayProperty=fullName>에서는 스레드가 이미 획득한 잠금을 다시 잠그려고 하면 예외를 throw하는 스레드 추적 모드를 지원합니다.  이 기능을 사용하면 잠금이 올바르게 종료되지 않은 지점을 보다 쉽게 찾을 수 있습니다.  <xref:System.Threading.SpinLock> 생성자를 사용하여 부울 입력 매개 변수를 받아서 `true`의 인수에 전달하여 스레드 추적 모드를 설정할 수 있습니다.  개발 및 테스트 단계를 완료한 후에는 보다 나은 성능을 위해 스레드 추적 모드를 해제합니다.  
  
## 예제  
 다음 예제에서는 스레드 추적 모드를 보여 줍니다.  잠금을 올바르게 종료하는 줄은 다음 결과 중 하나를 생성하는 코딩 오류를 시뮬레이션하도록 주석 처리됩니다.  
  
-   `true`\(Visual Basic의 경우 `True`\)의 인수를 사용하여 <xref:System.Threading.SpinLock>을 만든 경우 예외가 throw됩니다.  
  
-   `false`\(Visual Basic의 경우 `False`\)의 인수를 사용하여 <xref:System.Threading.SpinLock>을 만든 경우 교착 상태가 발생합니다.  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## 참고 항목  
 [SpinLock](../../../docs/standard/threading/spinlock.md)