---
title: "301 - UserDefinedErrorOccurred | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a0285d1c-550f-4c14-9c36-a96e97f1c4e4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 301 - UserDefinedErrorOccurred
## 속성  
  
|||  
|-|-|  
|ID|301|  
|키워드|문제 해결, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring|  
|수준|오류|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 이 이벤트는 사용자 코드에서 내보내집니다.개발자는 자신의 서비스에서 사용자 정의 오류가 발생할 때 이 이벤트를 내보낼 수 있습니다.이 작업은 <xref:System.Diagnostics.Eventing> API를 사용하여 수행할 수 있습니다.이외에도 이 API를 래핑하고 이 이벤트를 적절히 내보내는 방법을 보여 주는 WCF 샘플을 사용할 수도 있습니다.  
  
## 메시지  
 이름:'%1', 참조:'%2', 페이로드:%3  
  
## 세부 사항  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|이름|`xs:string`|이벤트의 사용자 정의 이름입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.이 서비스의 형식은 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'으로 정의됩니다.예를 들면 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'와 같습니다.|  
|Payload|`xs:string`|이벤트의 사용자 정의 페이로드입니다.|