---
title: "서비스: Calls Failed Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f1b196f3bed9b4e02963b090cf92a771d4bc5742
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="service-calls-failed-per-second"></a>서비스: Calls Failed Per Second
카운터 이름: Calls Failed Per Second  
  
## <a name="description"></a>설명  
 초당 이 서비스에서 받은, 처리되지 않은 예외가 있는 호출 수입니다.  
  
 이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.  
  
 (N 1 - N 0 ) / ( (D 1 -D 0 ) / F)  
  
 관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.  
  
 관리 코드에서 오류 조건이 발생하면 예외가 throw됩니다.  
  
 이 서비스에 처리되지 않은 예외가 있을 때마다 이 카운터가 증가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계약 및 서비스에서 오류 지정 및 처리](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
