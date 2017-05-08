---
title: "1150 - CompensationState | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1150 - CompensationState
## 속성  
  
|||  
|-|-|  
|ID|1150|  
|키워드|WFActivities|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 CompensableActivity에서 상태 변경을 나타냅니다.  
  
## 메시지  
 CompensableActivity '%1'은\(는\) '%2' 상태입니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|상태|xs:string|보정 상태입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|