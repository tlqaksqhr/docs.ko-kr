---
title: "404 - ResumeSignpostEvent | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 395cc7ca-f35f-4295-be97-39a077f99c97
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 404 - ResumeSignpostEvent
## 속성  
  
|||  
|-|-|  
|ID|404|  
|키워드|문제 해결|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 이 이벤트는 종단 간 동작의 다시 시작을 표시합니다.여기에는 동작의 이름이 포함됩니다.  
  
## 메시지  
 동작 경계입니다.  
  
## 세부 사항  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|Extended Data|`xs:string`|동작의 이름입니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|