---
title: "3550 - BufferOutOfOrderMessageNoInstance | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3550 - BufferOutOfOrderMessageNoInstance
## 속성  
  
|||  
|-|-|  
|ID|3550|  
|키워드|WFServices|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 버퍼링된 수신이 실패했음을 나타냅니다.  서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.  
  
## 메시지  
 현재는 '%1' 작업을 수행할 수 없습니다.  서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|OperationName|xs:string|작업의 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|