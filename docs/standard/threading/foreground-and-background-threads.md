---
title: "포그라운드 및 백그라운드 스레드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a>포그라운드 및 백그라운드 스레드
관리 되는 스레드는 백그라운드 스레드 또는 포그라운드 스레드입니다. 백그라운드 스레드는 한 가지 예외로 포그라운드 스레드 동일: 백그라운드 스레드에서 실행 하는 관리 되는 실행 환경을 유지 하지 않습니다. 관리 되는 프로세스 (.exe 파일은 관리 되는 어셈블리)에서 모든 포그라운드 스레드가 중지 된 후 시스템 모든 백그라운드 스레드를 중지 하 고 종료 합니다.  
  
> [!NOTE]
>  프로세스 종료 때문에 런타임에서 백그라운드 스레드가 중지 되 면 스레드에서 예외가 throw 됩니다. 그러나 스레드가 중단 되 면 때문에 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 메서드는 응용 프로그램 도메인을 언로드합니다는 <xref:System.Threading.ThreadAbortException> 전경색과 배경색 모두 스레드에서 throw 됩니다.  
  
 사용 하 여는 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> 속성 스레드는 배경이 나 전경 스레드 되는지 확인 하려면 나 해당 상태를 변경 합니다. 스레드 수 설정 변경할 수을 백그라운드 스레드로 언제 든 지 해당 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`합니다.  
  
> [!IMPORTANT]
>  스레드 포그라운드 또는 백그라운드 상태 결과 스레드에서 처리 되지 않은 예외가 적용 되지 않습니다. .NET Framework 버전 2.0에서에서 응용 프로그램이 종료 포그라운드 또는 백그라운드 스레드에서 처리 되지 않은 예외가 발생합니다. 참조 [관리 되는 스레드의 예외](../../../docs/standard/threading/exceptions-in-managed-threads.md)합니다.  
  
 관리 되는 스레드 풀에 속해 있는 스레드 (즉, 짝수인 스레드에 <xref:System.Threading.Thread.IsThreadPoolThread%2A> 속성은 `true`)는 백그라운드 스레드입니다. 비관리 코드에서 관리 되는 실행 환경에 들어가는 모든 스레드 백그라운드 스레드도 표시 됩니다. 만들고 새 시작에 의해 생성 된 모든 스레드가 <xref:System.Threading.Thread> 기본 포그라운드 스레드에서 개체입니다.  
  
 스레드를 사용 하 여 소켓 연결 등의 동작을 모니터링 하는 경우 설정의 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true` 스레드가 사용 해도 프로세스의 종료 되도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
