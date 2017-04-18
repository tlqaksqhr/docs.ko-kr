---
title: "System.ServiceModel.Channels.MsmqMessageRejected | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMessageRejected
MSMQ에서 메시지를 거부했습니다.  
  
## 설명  
 이 추적은 MSMQ 메시지가 거부되었음을 나타냅니다.  
  
 NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서 MSMQ 메시지를 처리할 수 없는 경우 MSMQ 메시지가 거부될 수 있습니다.이러한 메시지를 포이즌 메시지라고 합니다.포이즌 메시지는 NetMsmqBinding 또는 MsmqIntegrationBinding의 `ReceiveErrorHandling` 속성을 `Reject`로 설정할 경우 거부됩니다.거부된 메시지는 보낸 사람의 [배달 못 한 편지 큐](http://go.microsoft.com/fwlink/?LinkID=99544)로 전달됩니다.  
  
 메시지가 포이즌 메시지가 되는 경우 및 이러한 메시지를 적절하게 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546)\(영문 페이지일 수 있음\)를 참조하십시오.  
  
 MSMQ에서 거부된 메시지가 의미하는 것에 대한 자세한 내용은 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)를 참조하십시오.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)   
 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546)   
 [MQMarkMessageRejected](http://go.microsoft.com/fwlink/?LinkID=99548)