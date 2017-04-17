---
title: "System.ServiceModel.Channels.MsmqPoisonMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e64b9bd-1f12-43df-a189-d7be3c2bace1
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqPoisonMessageRejected
포이즌 메시지가 거부되었습니다.  
  
## 설명  
 이 추적은 포이즌 메시지가 발생되어 거부되었음을 나타냅니다.이는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 발생합니다.거부된 메시지는 보낸 사람의 [배달 못 한 편지 큐](http://go.microsoft.com/fwlink/?LinkId=99544)로 전달됩니다.  
  
 메시지가 포이즌 메시지가 되는 경우 및 이러한 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkId=99546)\(영문 페이지일 수 있음\)를 참조하십시오.MSMQ에서 거부된 메시지가 의미하는 것에 대한 자세한 내용은 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)를 참조하십시오.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkId=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkId=99548)