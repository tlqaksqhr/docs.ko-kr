---
title: "3552 - MaxPendingMessagesPerChannelExceeded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 3552 - MaxPendingMessagesPerChannelExceeded
## 속성  
  
|||  
|-|-|  
|ID|3552|  
|키워드|할당량, WFServices|  
|수준|경고|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 스로틀 'MaxPendingMessagesPerChannel' 한도에 도달했음을 나타냅니다.  
  
## 메시지  
 '%1'의 스로틀 'MaxPendingMessagesPerChannel' 한도에 도달했습니다.  이 한도를 늘리려면 BufferedReceiveServiceBehavior에서 MaxPendingMessagesPerChannel 속성을 조정하세요.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|Limit|xs:string|MaxPendingMessagesPerChannel 스로틀의 한도입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|