---
title: "끝점: Reliable Messaging Messages Dropped Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b6dc0763ef829c814b069488221ceb921e09b3d4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>끝점: Reliable Messaging Messages Dropped Per Second
카운터 이름: Reliable Messaging Sessions Dropped Per Second.  
  
## <a name="description"></a>설명  
 이 끝점에서 삭제된 신뢰할 수 있는 메시징 메시지의 초당 총 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
