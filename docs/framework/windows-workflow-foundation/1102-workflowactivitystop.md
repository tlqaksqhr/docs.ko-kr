---
title: "1102 - WorkflowActivityStop | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 285e5cb8-e90d-4914-ac06-e9b176ffefa2
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1102 - WorkflowActivityStop
## 속성  
  
|||  
|-|-|  
|ID|1102|  
|키워드|WFRuntime|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 워크플로 작업이 중지되었음을 나타냅니다.  
  
## 메시지  
 WorkflowInstance Id: '%1' E2E 작업  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|WorkflowInstanceId|xs:string|워크플로 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|