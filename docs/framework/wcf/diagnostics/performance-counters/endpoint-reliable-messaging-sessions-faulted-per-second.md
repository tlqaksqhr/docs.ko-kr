---
title: '끝점: Reliable Messaging Sessions Faulted Per Second'
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: 198acbeff6b8a54dcc6e4ae6966fea996da4b745
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472773"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a>끝점: Reliable Messaging Sessions Faulted Per Second
카운터 이름: Reliable Messaging Sessions Faulted Per Second.  
  
## <a name="description"></a>설명  
 초당 이 끝점에서 오류가 발생한 신뢰할 수 있는 메시징 세션의 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
