---
title: "Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3a4ead79-8550-4037-84e3-fd70ff56e001
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Microsoft.Transactions.TransactionBridge.RegisterParticipantFailure
WS\-AT 프로토콜 서비스가 제어 프로토콜에 대한 참가자를 등록하지 못했습니다.  
  
## 설명  
 MSDTC가 잘못된 등록 요청을 감지하는 경우 추적됩니다.이는 여러 완료 등록 요청 및 내부 오류에 의해 발생할 수 있습니다.  
  
## 문제 해결  
 완료를 두 번 이상 등록하지 마십시오.또한 추적 메시지 내의 상태 문자열을 검사하여 실행 가능한 항목이 있는지 확인하십시오.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)