---
title: Security Calls Not Authorized Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f189767-8c05-478a-8f0b-9228e5d351e5
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f52236bb69b1e393179e0a4a8af2e141c173d47d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="security-calls-not-authorized-per-second"></a>Security Calls Not Authorized Per Second
카운터 이름: Security Calls Not Authorized Per Second  
  
## <a name="description"></a>설명  
 이 작업에서 권한 부여에 실패한 초당 호출 횟수입니다.  
  
 이 카운터는 <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> 메서드가 `false`를 반환할 때 증가합니다. 들어오는 메시지가 올바른 사용자로부터 전송되고 적절하게 보호되지만 해당 사용자에게 특정 작업을 수행할 수 있는 권한이 없음을 나타냅니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)
