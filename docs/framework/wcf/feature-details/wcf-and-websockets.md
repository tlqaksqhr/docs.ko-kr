---
title: "WCF 및 웹 소켓 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e53b49e-022c-49c7-8984-4b21b53c05b3
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# WCF 및 웹 소켓
.NET Framework 4.5부터 Windows Communication Foundation에서 WebSocket을 지원합니다.WebSocket은 표준 HTTP 포트 80 및 443에서 양방향 통신을 가능하게 하는 효율적 표준 기반 기술입니다.표준 HTTP 포트를 사용하면 WebSocket이 매개자를 통해 웹에서 통신할 수 있습니다.WebSocket 전송에서 통신을 지원하기 위해<xref:System.ServiceModel.NetHttpBinding> 및 <xref:System.ServiceModel.NetHttpsBinding>이라는 두 가지 새 표준 바인딩이 추가되었습니다.WebSocket 관련 설정은 <xref:System.ServiceModel.Channels.HttpTransportBindingElement.WebSocketSettings%2A> 속성에 액세스하여 <xref:> System.ServiceModel.Channels.HttpTransportBinding?qualifyHint=False&autoUpgrade=True 요소에서 구성할 수 있습니다.  
  
## 단원 내용  
 [NetHttpBinding 사용](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)  
 <xref:System.ServiceModel.NetHttpBinding> 및 해당 구성 방법을 설명합니다.  
  
 [방법: WebSocket을 통해 통신하는 WCF 서비스 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-service-that-communicates-over-websockets.md)  
 WebSocket을 통해 통신하는 WCF 서비스를 만드는 방법을 설명합니다.  
  
## 참조  
  
## 관련 단원