---
title: "Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96474056-0418-41e4-8c75-bbc0a853eaba
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFailed
WS\-AT 프로토콜 서비스가 코디네이터에게 Register 메시지를 보내지 못했습니다.  
  
## 설명  
 로컬 TransactionManager가 메시지를 보낼 수 없기 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.  
  
## 문제 해결  
 메시지 보내기 오류의 원인인 예외에 대한 추적 메시지를 검사합니다.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)