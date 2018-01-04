---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24f74d4086a5499d3bfd4ef6183d377528acc21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="wsattracerecord"></a>WSAT_TraceRecord
WSAT_TraceRecord  
  
## <a name="syntax"></a>구문  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a>메서드  
 WSAT_TraceRecord 클래스는 메서드를 정의하지 않습니다.  
  
## <a name="properties"></a>속성  
 WSAT_TraceRecord 클래스에는 다음과 같은 속성이 있습니다.  
  
### <a name="activityid"></a>ActivityID  
 데이터 형식: object  
액세스 형식: 읽기 전용  
  
 추적 레코드의 동작 ID입니다.  
  
### <a name="eventid"></a>EventID  
 데이터 형식: sint32  
액세스 형식: 읽기 전용  
  
 추적 레코드의 이벤트 ID입니다.  
  
### <a name="tracerecord"></a>TraceRecord  
 데이터 형식: string  
액세스 형식: 읽기 전용  
  
 추적 레코드  
  
## <a name="requirements"></a>요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|-----------------------------------|  
|네임스페이스|root\ServiceModel에 정의되어 있습니다.|
