---
title: "213 - ServiceHostStarted | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6f7facc-342f-46bb-9d52-a470178ba6bb
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 213 - ServiceHostStarted
## 속성  
  
|||  
|-|-|  
|ID|213|  
|키워드|EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceHost|  
|수준|LogAlways|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 이 이벤트는 웹 호스팅 호스트가 시작될 때 내보내집니다.일반적으로 이러한 경우는 서비스가 메시지에 의해 활성화될 때 발생하며,서비스가 자동으로 시작되도록 구성된 경우에도 발생할 수 있습니다.  
  
## 메시지  
 ServiceHost 시작: '%1'.  
  
## 세부 사항  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|Service Type Name|`xs:string`|서비스 구현 형식의 CLR FullName입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.이 서비스의 형식은 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'으로 정의됩니다.예를 들면 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'와 같습니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|