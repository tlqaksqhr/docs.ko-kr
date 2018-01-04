---
title: "끝점: Calls Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 480e0758df7e3062f9bd2b0b089c7a9b75e1c012
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-calls-per-second"></a>끝점: Calls Per Second
카운터 이름: Calls Per Second  
  
## <a name="description"></a>설명  
 이 끝점에 대한 초당 호출 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
