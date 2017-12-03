---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b321f8c20fbd79b5e748601ee06f975dc75a7d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|1041|  
|키워드|WFRuntime|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그|  
  
## <a name="description"></a>설명  
 워크플로 응용 프로그램이 유휴 상태이며 지속 가능함을 나타냅니다. 워크플로 응용 프로그램이 유휴 상태이거나 지속됩니다.  
  
## <a name="message"></a>메시지  
 WorkflowApplication Id: '%1'는 유휴 상태로 지속 됩니다.  다음과 같은 조치가 취해집니다: %2입니다.  
  
## <a name="details"></a>세부 정보  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|워크플로 응용 프로그램 ID|  
|ActionTaken|xs:string|작업이 워크플로 응용 프로그램에서 수행됩니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
