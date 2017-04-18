---
title: "223 - OperationFaulted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 223 - OperationFaulted
## 속성  
  
|||  
|-|-|  
|ID|223|  
|키워드|EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel|  
|수준|경고|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 이 이벤트는 서비스 모델의 기본 `OperationInvoker`에서 해당 메서드를 호출하는 동안 `FaultException`에서 파생되는 예외가 발생하면 내보내집니다.  
  
## 메시지  
 OperationInvoker의 호출을 받은 '%1' 메서드에서 FaultException이 발생했습니다.메서드 호출 기간은 '%2'밀리초입니다.  
  
## 세부 사항  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|MethodName|`xs:string`|`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.|  
|Duration|`xs:long`|`OperationInvoker`가 메서드를 호출하는 데 걸린 시간\(밀리초\)입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.이 서비스의 형식은 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'으로 정의됩니다.예를 들면 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'와 같습니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|