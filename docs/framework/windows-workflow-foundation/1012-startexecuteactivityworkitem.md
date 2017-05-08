---
title: "1012 - StartExecuteActivityWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1012 - StartExecuteActivityWorkItem
## 속성  
  
|||  
|-|-|  
|ID|1012|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 ExecuteActivityWorkItem이 실행을 시작했음을 나타냅니다.  
  
## 메시지  
 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem 실행을 시작합니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|동작|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|