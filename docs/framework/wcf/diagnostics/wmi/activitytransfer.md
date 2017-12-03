---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c1caf0ae27efce858328e5db88434253be61d50
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="activitytransfer"></a>ActivityTransfer
활동 전송 이벤트  
  
## <a name="syntax"></a>구문  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a>메서드  
 ActivityTransfer 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 ActivityTransfer 클래스에는 다음 속성이 포함되어 있습니다.  
  
### <a name="activityid"></a>ActivityID  
  
-   데이터 형식: object  
    액세스 형식: 읽기 전용  
  
-   활동 ID  
  
### <a name="relatedactivityid"></a>RelatedActivityID  
  
-   데이터 형식: object  
    액세스 형식: 읽기 전용  
  
-   관련 활동 ID  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|
