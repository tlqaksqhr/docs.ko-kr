---
title: "트랜잭션 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
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
caps.handback.revision: 4
---
# 트랜잭션
이 단원에는 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 워크플로 트랜잭션을 사용하는 시나리오를 보여 주는 샘플이 포함되어 있습니다.  
  
## 단원 내용  
 [명령형 TransactionScope에서 워크플로 실행](../../../../docs/framework/windows-workflow-foundation/samples/execute-a-workflow-in-an-imperative-transactionscope.md)  
 명령형 C\# 코드에서 <xref:System.Transactions.Transaction>의 <xref:System.Activities.WorkflowInvoker>를 사용하여 워크플로를 실행하는 방법을 보여 줍니다.  
  
 [트랜잭션 호송 범위](../../../../docs/framework/windows-workflow-foundation/samples/transaction-convoy-scope.md)  
 <xref:System.ServiceModel.Activities.TransactedReceiveScope>와 함께 Parallel Convoy 메시징 활동 패턴을 만들어 동일한 트랜잭션 내에서 여러 작업을 순서에 관계 없이 진행할 수 있는 프로토콜을 모델링하는 방법을 보여 줍니다.  
  
 [트랜잭션 롤백](../../../../docs/framework/windows-workflow-foundation/samples/transaction-rollback.md)  
 앰비언트 <xref:System.Activities.RuntimeTransactionHandle>에 액세스하여 앰비언트 트랜잭션을 가져오고 이를 명시적으로 롤백하는 사용자 지정 <xref:System.Activities.NativeActivity>를 만드는 방법을 보여 줍니다.  
  
 [트랜잭션 범위 무시](../../../../docs/framework/windows-workflow-foundation/samples/suppress-transaction-scope.md)  
 앰비언트 런타임 트랜잭션이 있는 경우 이 트랜잭션을 표시하지 않도록 사용자 지정 `SuppressTransactionScope` 활동을 작성하는 방법을 보여 줍니다.  
  
 [트랜잭션된 큐](../../../../docs/framework/windows-workflow-foundation/samples/transacted-queues.md)  
 [!INCLUDE[wf1](../../../../includes/wf1-md.md)]에서 큐와 트랜잭션을 통합하여 안정적이고 확장 가능한 서비스를 만드는 방법을 보여 줍니다.