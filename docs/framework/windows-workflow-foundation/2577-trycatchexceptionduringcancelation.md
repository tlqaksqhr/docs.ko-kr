---
title: "2577 - TryCatchExceptionDuringCancelation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 2577 - TryCatchExceptionDuringCancelation
## 속성  
  
|||  
|-|-|  
|ID|2577|  
|키워드|WFActivities|  
|수준|경고|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 취소하는 동안 TryCatch 작업의 자식 작업에서 예외가 throw되었음을 나타냅니다.  
  
## 메시지  
 취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|