---
title: "2578 - TryCatchExceptionFromCatchOrFinally | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 2578 - TryCatchExceptionFromCatchOrFinally
## 속성  
  
|||  
|-|-|  
|ID|2578|  
|키워드|WFActivities|  
|수준|경고|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 Catch 또는 Finally 작업에서 예외가 throw되었음을 나타냅니다.  
  
## 메시지  
 TryCatch 작업 '%1'에 연결된 Catch 또는 Finally 작업에서 예외가 throw되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|