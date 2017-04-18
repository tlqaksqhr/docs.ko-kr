---
title: "트랜잭션 응용 프로그램 작성  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 트랜잭션 응용 프로그램 작성 
트랜잭션 응용 프로그램 프로그래머는 <xref:System.Transactions> 네임스페이스가 제공하는 두 가지 프로그래밍 모델을 활용하여 트랜잭션을 만들 수 있습니다.<xref:System.Transactions.Transaction> 클래스를 사용하여 명시적 프로그래밍 모델을 사용하거나 <xref:System.Transactions.TransactionScope> 클래스를 사용하여 트랜잭션이 인프라에 의해 자동으로 관리되는 암시적 프로그래밍 모델을 사용할 수 있습니다.개발 시에는 암시적 트랜잭션 모델을 사용하는 것이 좋습니다.[트랜잭션 범위를 사용하여 암시적 트랜잭션 구현 ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) 항목에서 트랜잭션 범위의 사용 방법에 대한 자세한 내용을 볼 수 있습니다.  
  
 두 모델은 모두 프로그램이 일관된 상태에 도달할 때 트랜잭션을 커밋하는 기능을 지원합니다.커밋이 성공하면 트랜잭션이 영구적으로 커밋됩니다.커밋이 실패하면 트랜잭션이 중단됩니다.응용 프로그램에서 트랜잭션을 성공적으로 완료할 수 없는 경우 트랜잭션을 중단하고 그 결과를 취소합니다.  
  
## 단원 내용  
  
### 트랜잭션 만들기  
 <xref:System.Transactions> 네임스페이스에서는 트랜잭션을 만드는 두 가지 모델을 제공합니다.이 모델에 대해서는 다음 항목에서 설명합니다.  
  
 [트랜잭션 범위를 사용하여 암시적 트랜잭션 구현 ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 <xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.TransactionScope> 클래스를 사용하여 암시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.  
  
 [CommittableTransaction을 사용하여 명시적 트랜잭션 구현 ](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 <xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.CommittableTransaction> 클래스를 사용하여 명시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.  
  
### 트랜잭션 관리 에스컬레이션  
 트랜잭션이 다른 응용 프로그램 도메인의 리소스에 액세스해야 하는 경우 또는 다른 지속적인 리소스 관리자를 참여시키려는 경우 트랜잭션이 MSDTC에 의해 관리되도록 자동으로 에스컬레이션됩니다.트랜잭션 에스컬레이션에 대해서는 [트랜잭션 관리 에스컬레이션 ](../../../../docs/framework/data/transactions/transaction-management-escalation.md) 항목에서 설명합니다.  
  
### 동시성  
 [DependentTransaction으로 동시성 관리 ](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) 항목에서는 <xref:System.Transactions.DependentTransaction> 클래스를 사용하여 비동기 작업 간의 동시성을 유지하는 방법에 대해 설명합니다.  
  
### COM\+ Interop  
 [엔터프라이즈 서비스 및 COM\+ 트랜잭션과의 상호 운용성 ](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) 항목에서는 분산 트랜잭션이 COM\+ 트랜잭션과 상호 작용하도록 설정하는 방법에 대해 설명합니다.  
  
### 진단  
 [진단 추적 ](../../../../docs/framework/data/transactions/diagnostic-traces.md)에서는 <xref:System.Transactions> 인프라에서 생성된 추적 코드를 사용하여 응용 프로그램 오류를 해결하는 방법에 대해 설명합니다.  
  
### ASP.NET 작업  
 [ASP.NET에서 System.Transactions 사용](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) 항목에서는 ASP.NET 응용 프로그램 내부에서 <xref:System.Transactions>를 성공적으로 사용하는 방법에 대해 설명합니다.