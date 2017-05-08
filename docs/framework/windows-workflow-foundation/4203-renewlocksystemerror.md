---
title: "4203 - RenewLockSystemError | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4203 - RenewLockSystemError
## 속성  
  
|||  
|-|-|  
|ID|4203|  
|키워드|WFInstanceStore|  
|수준|오류|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었기 때문에 SQL 공급자가 잠금 만료를 연장하지 못했음을 나타냅니다.  SqlWorkflowInstanceStore가 중단됩니다.  
  
## 메시지  
 잠금 만료를 연장하지 못했습니다. 잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었습니다.  SqlWorkflowInstanceStore를 중단하는 중입니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|