---
title: "System.ServiceModel.Channels.ConnectionPoolCloseException | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8358898e-129e-4fac-a6bf-bf3aa4293ae2
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# System.ServiceModel.Channels.ConnectionPoolCloseException
이 연결 풀에서 연결을 닫는 동안 예외가 발생했습니다.  
  
## 설명  
 이 오류 수준 추적은 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]의 연결 풀링 기능에서 사용하는 연결 풀을 닫는 동안 오류가 발생했음을 나타냅니다.이러한 오류의 원인 중 하나는 CloseTimeout 내의 풀 연결 또는 풀 연결 집합을 닫는 데 실패한 것입니다.이 예외가 throw되면 해당 풀 내의 닫지 않은 나머지 연결이 중단되고 다른 풀 내의 닫지 않은 연결도 중단됩니다.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)