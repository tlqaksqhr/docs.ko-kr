---
title: "1041 - WorkflowApplicationPersistableIdle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1041 - WorkflowApplicationPersistableIdle
## 속성  
  
|||  
|-|-|  
|ID|1041|  
|키워드|WFRuntime|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 워크플로 응용 프로그램이 유휴 상태이며 지속 가능함을 나타냅니다.  워크플로 응용 프로그램이 유휴 상태이거나 지속됩니다.  
  
## 메시지  
 WorkflowApplication Id: '%1'이\(가\) 유휴 상태로 지속됩니다. 다음 작업이 수행됩니다. %2.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|WorkflowApplicationId|xs:string|워크플로 응용 프로그램 ID|  
|ActionTaken|xs:string|작업이 워크플로 응용 프로그램에서 수행됩니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|