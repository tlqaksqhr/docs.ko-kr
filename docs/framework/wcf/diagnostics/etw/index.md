---
title: "Analytic Tracing with ETW | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "diagnostics [WCF], analytic tracing"
  - "administration [WCF], analytic tracing"
  - "analytic tracing [WCF]"
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Analytic Tracing with ETW
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 분석 추적을 사용하면 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 실행하는 동안 진단 정보를 캡처할 수 있습니다.프로덕션 환경에서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스 문제를 해결할 수 있도록 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 스택의 주요 시점에[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 분석 추적 이벤트를 내보냅니다.[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스의 분석 추적은 ETW\(Event Tracing for Windows\) 세션에 매우 효율적으로 내보내지므로 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 서비스를 호스팅하는 프로덕션 서버의 성능에 최소한의 영향만 줍니다.  
  
## 단원 내용  
 [분석 추적 개요](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)]에서 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 분석 추적을 사용하는 방법에 대해 설명합니다.  
  
 [동적으로 분석 추적을 사용하도록 설정](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 ETW를 사용하여 추적을 동적으로 사용하거나 사용하지 않도록 설정하는 방법에 대해 설명합니다.  
  
 [메시지 흐름 추적 구성](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 메시지 흐름 추적을 구성하는 방법에 대해 설명합니다.  
  
 [분석 추적 이벤트 참조](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 이벤트 ID와 함께 해당 이벤트 수준, 이벤트 메시지 및 키워드가 포함된 표를 보여 줍니다.  
  
## 참고 항목  
 [Windows용 WCF 서비스 및 이벤트 추척](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)   
 [Windows에서 이벤트 추적으로 이벤트 추적](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)