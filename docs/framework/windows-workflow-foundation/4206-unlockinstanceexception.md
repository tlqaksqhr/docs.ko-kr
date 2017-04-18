---
title: "4206 - UnlockInstanceException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 4206 - UnlockInstanceException
## 속성  
  
|||  
|-|-|  
|ID|4206|  
|키워드|WFInstanceStore|  
|수준|오류|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 인스턴스를 잠금 해제하려는 동안 예외가 발생했음을 나타냅니다.  
  
## 메시지  
 인스턴스 잠금을 해제하는 동안 %1 예외가 발생했습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|ExceptionMessage|xs:string|SQL 예외로부터의 메시지입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|