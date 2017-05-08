---
title: "4202 - StartSqlCommandExecute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4559f64f-c824-4075-9e7e-4710bf30f805
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4202 - StartSqlCommandExecute
## 속성  
  
|||  
|-|-|  
|ID|4202|  
|키워드|WFInstanceStore|  
|수준|Verbose|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 SQL 명령이 실행되고 있음을 나타냅니다.  
  
## 메시지  
 SQL 명령 실행 시작: %1  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|SqlCommand|xs:string|실행된 SQL 명령입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|