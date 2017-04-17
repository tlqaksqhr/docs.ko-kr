---
title: "신뢰할 수 있는 세션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Windows Communication Foundation, sessions and instances"
  - "WCF, sessions and instances"
  - "sessions and instances [WCF]"
helpviewer_keywords: 
  - "인스턴스 [WCF]"
  - "세션 [WCF]"
ms.assetid: 143951b3-3aa0-4540-b4b7-d33e77e874a1
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# 신뢰할 수 있는 세션
이 단원에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 신뢰할 수 있는 세션에 대한 정의, 용도, 사용 방법과 사용 시기, 이를 지원하는 바인딩 구성 및 몇 가지 최선의 방법에 대해 설명합니다.다음 표에서는 이 단원의 필수 사항 및 관련 항목에 대한 세부 정보를 요약하여 설명합니다.  
  
 신뢰할 수 있는 세션 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 끝점 간에 보내진 메시지가 SOAP 또는 전송 매개자를 통해 전송되도록 하고 보내진 순서대로 한 번만 선택적으로 배달되도록 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램에서 신뢰할 수 있는 세션을 사용하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 신뢰할 수 있는 세션을 기본적으로 또는 선택 사항으로 지원하는 시스템 제공 바인딩 중 하나를 사용하거나 이러한 세션을 지원하는 사용자 지정 바인딩을 직접 만듭니다.  
  
## 단원 내용  
 [신뢰할 수 있는 세션 개요](../../../../docs/framework/wcf/feature-details/reliable-sessions-overview.md)  
 신뢰할 수 있는 세션, 사용 시기, 신뢰할 수 있는 세션을 지원하는 다른 바인딩 및 그러한 바인딩의 작동 방식에 대해 설명합니다.  
  
 [방법: 신뢰할 수 있는 세션 내에서 메시지 교환](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md)  
 구성에 지정된 사용자 지정 바인딩을 사용하여 HTTP를 통해 신뢰할 수 있는 세션을 만드는 방법에 대해 설명합니다.  
  
 [방법: 신뢰할 수 있는 세션 내에서 메시지 보안](../../../../docs/framework/wcf/feature-details/how-to-secure-messages-within-reliable-sessions.md)  
 신뢰할 수 있는 세션의 보안을 유지하는 방법에 대해 설명합니다.  
  
 [방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)  
 HTTPS를 통해 신뢰할 수 있는 세션을 만드는 방법에 대해 설명합니다.  
  
 [신뢰할 수 있는 세션을 위한 최선의 방법](../../../../docs/framework/wcf/feature-details/best-practices-for-reliable-sessions.md)  
 신뢰할 수 있는 세션 사용과 관련된 몇 가지 최선의 방법에 대해 설명합니다.  
  
## 참조  
 <xref:System.ServiceModel.ReliableSession>  
  
## 참고 항목  
 [큐 및 신뢰할 수 있는 세션](../../../../docs/framework/wcf/feature-details/queues-and-reliable-sessions.md)   
 [세션, 인스턴스 및 동시성](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)