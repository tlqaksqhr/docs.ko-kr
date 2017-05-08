---
title: "System.ServiceModel.ManualFlowThrottleLimitReached | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9aba851f-1830-493b-8e3e-60f454eb923e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# System.ServiceModel.ManualFlowThrottleLimitReached
System.ServiceModel.ManualFlowThrottleLimitReached  
  
## 설명  
 시스템이 ManualFlowControlLimit 스로틀에 대해 설정된 제한에 도달했습니다.스로틀 값은 ServiceHost 또는 InstanceContext에서 ManualFlowControlLimit 속성을 수정하여 변경할 수 있습니다.  
  
 수동 흐름 제어 제한을 처음에 0으로 줄인 경우 이 추적을 내보냅니다.다음에 0으로 변경하면 추적되지 않습니다.인스턴스 컨텍스트에 대한 흐름 제어 제한은 각 컨텍스트에 대해 한 번 추적됩니다.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)