---
title: "1132 - InvokeMethodDoesNotUseAsyncPattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1132 - InvokeMethodDoesNotUseAsyncPattern
## 속성  
  
|||  
|-|-|  
|ID|1132|  
|키워드|WFRuntime|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용하지 않음을 나타냅니다.  
  
## 메시지  
 InvokeMethod '%1' \- 메서드에서 비동기 패턴을 사용하지 않습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|InvokeMethod|xs:string|InvokeMethod 작업의 표시 이름입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|