---
title: "System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d75d39da-7502-4a6a-91b9-eaa05b8e24d5
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# System.ServiceModel.Channels.MsmqMoveOrDeleteAttemptFailed
메시지를 이동하거나 삭제할 수 없습니다.  
  
## 설명  
 이 추적은 MSMQ 메시지를 이동, 삭제 및 거부하는 동안 오류가 발생했음을 나타냅니다.  
  
 NetMsmqBinding 또는 MsmqIntegrationBinding과 함께 사용하는 경우 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 MSMQ 메시지를 사용합니다. 이 추적은 NetMsmqBinding 또는 MsmqIntegrationBinding의 선택한 `ReceiveErrorHandling` 속성 값과 관련됩니다.  
  
 이 추적은 전체 시스템 오류를 의미하지는 않습니다.  그러나 메시지에서 선택한 포이즌 메시지를 처리하지 못했음을 나타냅니다.  메시지가 포이즌이 되는 경우와 이러한 메시지를 적절히 처리하도록 서비스를 구성하는 방법에 대한 자세한 내용은 [포이즌 메시지 처리](http://go.microsoft.com/fwlink/?LinkID=99546)를 참조하세요.  
  
## 참고 항목  
 [추적](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [추적을 사용하여 응용 프로그램 문제 해결](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [관리 및 진단](../../../../../docs/framework/wcf/diagnostics/index.md)