---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 803616fdd287491afa27d3ac23dfce99c5db08ca
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="57398---maxinstancesexceeded"></a>57398 - MaxInstancesExceeded
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|57398|  
|키워드|WFServices|  
|수준|경고|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 시스템이 스로틀 'MaxConcurrentInstances'에 대해 설정된 한도에 도달했음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 시스템이 'MaxConcurrentInstances' 스로틀에 대해 설정된 한계에 도달했습니다. 이 스로틀에 대한 제한은 %1(으)로 설정되었습니다. serviceThrottle 요소에서 'maxConcurrentInstances' 특성을 수정하거나 ServiceThrottlingBehavior 동작에서 'MaxConcurrentInstances' 속성을 수정하여 스로틀 값을 변경할 수 있습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|이름|xs:string|항목의 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
