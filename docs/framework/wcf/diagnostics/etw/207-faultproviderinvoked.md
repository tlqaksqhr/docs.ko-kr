---
title: "207 - FaultProviderInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 207 - FaultProviderInvoked
## 속성  
  
|||  
|-|-|  
|ID|207|  
|키워드|문제 해결, ServiceModel|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 이 이벤트는 `FaultProvider`가 호출된 후에 내보내집니다.  
  
## 메시지  
 디스패처가 '%2' 형식의 예외와 함께 '%1' 형식의 FaultProvider를 호출했습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|TypeName|`xs:string`|호출된 `FaultProvider` 형식의 CLR FullName입니다.|  
|ExceptionTypeName|`xs:string`|`FaultProvider`가 처리한 예외의 CLR FullName입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.  이 서비스의 형식은 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'으로 정의됩니다.  예를 들면 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'와 같습니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|