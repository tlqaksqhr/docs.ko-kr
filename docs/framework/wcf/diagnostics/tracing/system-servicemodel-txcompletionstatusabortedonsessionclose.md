---
title: "System.ServiceModel.TxCompletionStatusAbortedOnSessionClose | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e142e9d-e81b-4309-974a-02e9cc064ea0
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.TxCompletionStatusAbortedOnSessionClose
세션을 닫고 TransactionAutoCompleteOnSessionClose OperationBehaviorAttribute가 false로 설정되었을 때 지정된 트랜잭션이 완료되지 않았기 때문에 해당 트랜잭션이 중단되었습니다.  
  
## 설명  
 현재 활성 세션을 닫고 트랜잭션이 완료되지 않았으며 TransactionAutoCompleteOnSessionClose가 `false`로 설정된 경우 추적됩니다.  
  
## 문제 해결  
 이 추적은 조사해야 하는 발생 가능한 응용 프로그램 버그를 나타냅니다.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)