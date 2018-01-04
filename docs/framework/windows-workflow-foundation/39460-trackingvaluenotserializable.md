---
title: 39460 - TrackingValueNotSerializable
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 476a29ad-24d8-4359-8c17-d4e20c1e1c15
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d33c17f212f5413732fe982cf7ea06a610df0d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="39460---trackingvaluenotserializable"></a>39460 - TrackingValueNotSerializable
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|39460|  
|키워드|WFTracking|  
|수준|경고|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 추적 레코드에서 추출된 인수/변수는 Serialize할 수 없습니다.  
  
## <a name="message"></a>메시지  
 추출된 인수/변수 '%1'은(는) serialize할 수 없습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|이름|xs:string|항목의 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
