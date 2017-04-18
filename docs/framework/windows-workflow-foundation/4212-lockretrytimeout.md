---
title: "4212 - LockRetryTimeout | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4212 - LockRetryTimeout
## 속성  
  
|||  
|-|-|  
|ID|4212|  
|키워드|WFInstanceStore|  
|수준|경고|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 SQL 공급자에서 인스턴스 잠금을 얻으려는 중 시간 초과가 발생했습니다.  
  
## 메시지  
 인스턴스 잠금을 얻으려는 중 시간이 초과했습니다. 할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.  이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|Delay|xs:string|재시도 사이의 지연입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|