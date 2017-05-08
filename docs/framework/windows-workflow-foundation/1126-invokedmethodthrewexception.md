---
title: "1126 - InvokedMethodThrewException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 1126 - InvokedMethodThrewException
## 속성  
  
|||  
|-|-|  
|ID|1126|  
|키워드|WFRuntime|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.  
  
## 메시지  
 작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다.  %2  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|InvokeMethod|xs:string|InvokeMethod 작업의 표시 이름입니다.|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|