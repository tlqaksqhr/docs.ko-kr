---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 346cb98b1285883a9a85f2c7abb6147f42734395
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="3508---trackingprofilenotfound"></a>3508 - TrackingProfileNotFound
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|3508|  
|키워드|WFServices|  
|수준|Verbose|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 프로필과 일치하지 않음을 나타냅니다.  
  
## <a name="message"></a>메시지  
 ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다. 구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|TrackingProfile|xs:string|추적 프로필의 이름입니다.|  
|ActivityDefinitionId|xs:string|작업 정의 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
