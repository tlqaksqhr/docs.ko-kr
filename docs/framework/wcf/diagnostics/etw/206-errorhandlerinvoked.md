---
title: "206 - ErrorHandlerInvoked | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 206 - ErrorHandlerInvoked
## 속성  
  
|||  
|-|-|  
|ID|206|  
|키워드|문제 해결, ServiceModel|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 이 이벤트는 서비스 작업에서 발생한 예외를 처리할 수 있는 기회가 `ErrorHandler`에 제공된 후에 내보내집니다.  
  
## 메시지  
 디스패처가 '%3' 형식의 예외와 함께 '%1' 형식의 ErrorHandler를 호출했습니다.ErrorHandled \=\= '%2'.  
  
## 세부 사항  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|TypeName|`xs:string`|호출된 `ErrorHandler` 형식의 CLR FullName입니다.|  
|Handled|`xs:unsignedByte`|오류 처리기가 오류를 처리했으면 `true`이고, 그렇지 않으면 `false`입니다.|  
|ExceptionTypeName|`xs:string`|처리된 예외의 CLR FullName입니다.|  
|HostReference|`xs:string`|웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.이 서비스의 형식은 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'으로 정의됩니다.예를 들면 'Default Web Site\/CalculatorApplication&#124;\/CalculatorService.svc&#124;CalculatorService'와 같습니다.|  
|AppDomain|`xs:string`|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|