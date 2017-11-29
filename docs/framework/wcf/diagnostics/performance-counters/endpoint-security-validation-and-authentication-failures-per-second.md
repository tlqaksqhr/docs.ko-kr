---
title: "끝점: Security Validation and Authentication Failures Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89a70b90-d7e4-4b03-9b84-4dc88ce3d605
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c6b50aa00fe59d0ad23d5ca0b77c7b89f97a0d1e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-security-validation-and-authentication-failures-per-second"></a>끝점: Security Validation and Authentication Failures Per Second
카운터 이름: Security Validation and Authentication Failures Per Second  
  
## <a name="description"></a>설명  
 이 카운터는 "Security Calls Not Authorized" 카운터로 처리되지 않는 보안 문제 때문에 메시지가 거부될 때마다 증가합니다. 이러한 문제는 다음과 같습니다.  
  
-   클라이언트 토큰을 메시지에서 읽을 수 없습니다.  
  
-   클라이언트 토큰에서 인증에 실패했습니다(예: 잘못된 암호).  
  
-   서명 확인에 실패했습니다(예: 메시지 변조).  
  
-   메시지가 이전 메시지와 중복됩니다. 이러한 현상은 재생 공격 중에 나타날 수 있습니다.  
  
-   해독 오류가 발생했습니다.  
  
-   일부 필수 요소(예: 타임스탬프 또는 암호화된 데이터 블록)가 메시지에 없습니다.  
  
-   TLSNEGO/SPNEGO 핸드셰이크 중에 오류가 발생했습니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음 수식을 사용 하 여 계산 됩니다.  
  
 (N1-N0)/((D1-D0)/F)
