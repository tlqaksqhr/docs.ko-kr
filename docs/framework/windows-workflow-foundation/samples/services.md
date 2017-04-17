---
title: "서비스 (Windows Workflow) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 521cdb66-98cb-4ad1-b706-370788a43485
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 서비스 (Windows Workflow)
이 단원에는 워크플로 서비스를 사용하는 시나리오를 보여 주는 샘플이 포함되어 있습니다.  
  
## 단원 내용  
 [OperationScope](../../../../docs/framework/windows-workflow-foundation/samples/operationscope.md)  
 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 메시지 활동을 사용하여 기존 사용자 지정 활동을 워크플로 서비스에 작업으로 노출하는 방법을 보여 줍니다.  
  
 [OperationContext 액세스](../../../../docs/framework/windows-workflow-foundation/samples/accessing-operationcontext.md)  
 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.Send> 메시징 활동을 사용자 지정 범위 활동에 사용하여 <xref:System.ServiceModel.OperationContext.Current%2A>에 액세스하고 보내거나 들어오는 메시지 내의 사용자 지정 메시지 헤더를 검색하거나 첨부하는 방법을 보여 줍니다.  
  
 [LINQ 메시지 쿼리 상관 관계](../../../../docs/framework/windows-workflow-foundation/samples/linq-message-query-correlation.md)  
 시스템에서 제공하는 <xref:System.ServiceModel.XPathMessageQuery> 대신 사용자 지정 <xref:System.ServiceModel.Dispatcher.MessageQuery> 구현을 사용하여 내용 기반 상관 관계를 만드는 방법을 보여 줍니다.  
  
 [상호 관련된 계산기](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)  
 디자이너에서 메시지의 매개 변수를 기준으로 내용 기반 상관 관계에 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 메시징 활동을 사용하는 방법을 보여 줍니다.  
  
 [워크플로 서비스에 보안 설정](../../../../docs/framework/windows-workflow-foundation/samples/securing-workflow-services.md)  
 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 활동을 사용하는 기본 워크플로 서비스를 만들고 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 구성을 사용하여 워크플로 서비스에 사용할 보안 끝점을 정의하는 방법을 보여 줍니다.  
  
 [Asynchronous Communication](../../../../docs/framework/windows-workflow-foundation/samples/asynchronous-communication.md)  
 서로 다른 두 [!INCLUDE[wf](../../../../includes/wf-md.md)] 서비스 사이의 통신이 기본적으로 비동기적인 방식에 의해 이루어진다는 사실을 보여 줍니다.