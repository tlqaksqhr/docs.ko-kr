---
title: "스레드 스케줄링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], scheduling
- scheduling threads
ms.assetid: 67e4a0eb-3095-4ea7-b20f-908faa476277
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e1fb7d61b8e250884b2c57cad8c5106bc77787a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="scheduling-threads"></a>스레드 스케줄링
모든 스레드에 할당 된 스레드 우선 순위를 있습니다. 공용 언어 런타임 내에서 만들어진 스레드는 처음의 우선 순위를 할당 **ThreadPriority.Normal**합니다. 런타임 외부에서 만든 스레드가 관리 되는 환경을 입력 한다 전의 우선 순위를 유지 합니다. 가져오거나와 모든 스레드의 우선 순위를 설정할 수는 **Thread.Priority** 속성입니다.  
  
 우선 순위에 따라 실행 스레드가 예약 됩니다. 스레드 런타임 내에서 실행 하는 경우에 모든 스레드는 운영 체제에서 프로세서 시간 조각 할당 됩니다. 스레드가 실행 되는 순서를 결정 하는 데 사용 되는 일정 알고리즘의 세부 정보는 각 운영 체제에 따라 다릅니다. 일부 운영 체제 (실행 될 수 있는 스레드) 중 가장 높은 우선 순위를 가진 스레드는 항상 첫 번째 실행 되도록 예약 됩니다. 우선 순위가 같은 여러 스레드를 모두 사용할 수 있으면 스케줄러 순환 해당 우선 순위의 스레드 각 스레드를 실행할 고정된 시간 간격을 제공 합니다. 더 높은 우선 순위를 가진 스레드는 실행할 수 있습니다.,으로 우선 순위가 낮은 스레드가 실행을 얻지 못합니다. 지정 된 우선 순위에서 스레드를 더 이상 실행할 수 없는 경우 스케줄러 다음 낮은 우선 순위를 이동 하 고 실행을 위해 해당 우선 순위의 스레드를 예약 합니다. 더 높은 우선 순위 스레드 실행 가능 해지면 낮은 우선 순위 스레드 비워진 및 더 높은 우선 순위 스레드는 한 번 다시 실행할 수 있습니다. 모든 문제를 기반으로 운영 체제 조정할 수도 스레드 우선 순위 동적으로 응용 프로그램의 사용자 인터페이스를 전경색과 배경색 간에 이동할 때. 다른 운영 체제 다른 일정 알고리즘을 사용 하도록 선택할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레드 및 스레딩 사용](../../../docs/standard/threading/using-threads-and-threading.md)  
 [Windows에서 관리되는 스레딩 및 관리되지 않는 스레딩](../../../docs/standard/threading/managed-and-unmanaged-threading-in-windows.md)
