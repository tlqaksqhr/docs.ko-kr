---
title: "39460 - TrackingValueNotSerializable | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 476a29ad-24d8-4359-8c17-d4e20c1e1c15
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 39460 - TrackingValueNotSerializable
## 속성  
  
|||  
|-|-|  
|ID|39460|  
|키워드|WFTracking|  
|수준|경고|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 추적 레코드에서 추출된 인수\/변수는 Serialize할 수 없습니다.  
  
## 메시지  
 추출된 인수\/변수 '%1'은\(는\) serialize할 수 없습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|이름|xs:string|항목의 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|