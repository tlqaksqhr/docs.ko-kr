---
title: "System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 155c3203-2e17-4709-b896-2254e22da45e
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# System.ServiceModel.TxCompletionStatusCompletedForAsyncAbort
비동기 중단으로 인해 지정된 작업에 대한 지정된 트랜잭션이 완료되었습니다.  
  
## 설명  
 다른 참가자가 중단을 응답하거나, 시간 초과가 발생하거나, 트랜잭션 참가자 내부에서 다른 오류가 발생하여 현재 트랜잭션이 중단되었습니다.  
  
## 문제 해결  
 이 중단이 예기치 않은 동작인 경우 모든 시스템 로그에서 실제 중단 이유를 확인합니다.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)