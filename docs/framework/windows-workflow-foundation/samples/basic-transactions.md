---
title: "트랜잭션 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
---
# 트랜잭션
이 단원에는 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 워크플로 트랜잭션을 보여 주는 샘플이 포함되어 있습니다.  
  
## 단원 내용  
 [기본 TransactionScope](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <xref:System.Activities.Statements.TransactionScope> 인스턴스를 중첩하는 방법을 보여 주는 네 개의 시나리오로 구성되어 있습니다.  
  
 [TransactedReceiveScope 사용](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <xref:System.Activities.Statements.TransactionScope>를 사용하여 클라이언트에 새 트랜잭션을 만들고 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용하여 이동된 트랜잭션과 함께 메시지를 받고 서버에 있는 트랜잭션의 수명 주기 범위를 지정하여 클라이언트에서 서버로 트랜잭션을 이동하는 방법을 보여 줍니다.  
  
 [서비스 내에 TransactionScope 중첩](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 한 서비스 내의 <xref:System.Activities.Statements.TransactionScope> 활동 인스턴스를 처리하는 방법을 보여 주는 두 개의 시나리오로 구성되어 있습니다.