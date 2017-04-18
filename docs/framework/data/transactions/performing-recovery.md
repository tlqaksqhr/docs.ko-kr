---
title: "복구 수행  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6dd17bf6-ba42-460a-a44b-8046f52b10d0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 복구 수행 
리소스 관리자는 리소스 오류가 발생한 후에 트랜잭션 참가 요소를 다시 참여시켜 트랜잭션에서 영속적 참여 항목을 쉽게 확인할 수 있도록 합니다.  
  
## 복구 프로세스  
 <xref:System.Transactions.IEnlistmentNotification> 인터페이스 구현에서 설명한 대로 나중에 복구할 수 있는 리소스를 지속적으로 참여시키려면 <xref:System.Transactions.Transaction.EnlistDurable%2A> 메서드를 호출해야 합니다.또한 리소스 오류가 발생할 경우 트랜잭션 참가자에 일관성 있게 레이블을 지정하는 데 사용되는 리소스 관리자 식별자\(<xref:System.Guid>\)를 <xref:System.Transactions.Transaction.EnlistDurable%2A> 메서드에 제공해야 합니다.이런 이유로 초기 인리스트먼트 호출에 제공되는 <xref:System.Guid>는 복구 중에 <xref:System.Transactions.TransactionManager.Reenlist%2A> 호출의 *resourceManagerIdentifier* 매개 변수와 같아야 합니다.그렇지 않으면 <xref:System.Transactions.TransactionException>이 throw됩니다.지속적인 인리스트먼트에 대한 자세한 내용은 [리소스를 트랜잭션에 참가 요소로 등록 ](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)을 참조하십시오.  
  
 2PC 프로토콜의 준비 단계\(1단계\)에서 지속적인 리소스 관리자의 구현이 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 알림을 받는 경우 이 단계 중에 준비 레코드를 기록해야 합니다.이 레코드에는 커밋 시 트랜잭션을 완료하는 데 필요한 모든 정보가 들어 있어야 합니다.나중에 *preparingEnlistment* 콜백의 <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> 속성을 검색하여 복구 중에 준비 레코드에 액세스할 수 있습니다.<xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 메서드 내에서 레코드 로깅을 수행하지 않아도 됩니다. RM이 작업자 스레드에서 이 작업을 수행할 수 있습니다.  
  
 복구 프로세스는 다음 두 단계로 이루어집니다.  
  
### 1단계 \- ReEnlist  
 리소스 관리자는 준비 정보 레코드에서 불확실한 각 인리스트먼트를 검사합니다.1단계 중에 <xref:System.Transactions.IEnlistmentNotification.Prepare%2A> 알림에 포함되어 리소스 관리자에게 전달되는 <xref:System.Transactions.PreparingEnlistment> 콜백의 <xref:System.Transactions.PreparingEnlistment.RecoveryInformation%2A> 속성을 검사하면 됩니다.  
  
 리소스 관리자는 검사하는 각 인리스트먼트에 대해 트랜잭션 관리자에서 <xref:System.Transactions.TransactionManager.Reenlist%2A>를 호출합니다.이 메서드는 리소스 관리자를 식별하는 고유한 <xref:System.Guid>와 바이트 배열로 인터페이스 정보를 전달합니다.새 <xref:System.Transactions.Enlistment> 개체가 반환됩니다.예외가 발생하여 인리스트먼트 재시도가 실패하면 리소스 관리자가 나중에 다시 시도해야 합니다.  
  
 오류 발생 후 리소스 관리자가 다시 시작될 때만 <xref:System.Transactions.TransactionManager.Reenlist%2A> 메서드를 호출해야 합니다.또한 2단계 커밋의 초기 준비 단계에서 리소스 관리자가 로그한 미해결된 트랜잭션만 다시 참여시켜야 합니다.알맞지 않은 시기에 이 메서드를 호출하려고 하면 잘못된 결과가 생성될 수 있습니다.  
  
 이 메서드를 사용하여 참가 요소가 다시 참여되면 트랜잭션 결과에 해당하는 <xref:System.Transactions.IEnlistmentNotification>의 2단계 메서드\(즉, <xref:System.Transactions.IEnlistmentNotification.Commit%2A> , <xref:System.Transactions.IEnlistmentNotification.Rollback%2A> 또는 <xref:System.Transactions.IEnlistmentNotification.InDoubt%2A>\)가 알맞게 호출됩니다.  
  
### 2단계 \- 복구 완료  
 인리스트먼트 재시도가 모두 완료되면 리소스 관리자가 <xref:System.Transactions.TransactionManager.RecoveryComplete%2A> 메서드를 호출합니다.이 메서드는 복구를 완료하고 리소스 관리자에 더 이상 불확실한 트랜잭션이 없음을 트랜잭션 관리자에게 알립니다.이렇게 함으로써 리소스 관리자는 <xref:System.Transactions.TransactionManager.Reenlist%2A> 메서드를 다시 호출하지 않도록 합니다.  
  
 리소스 관리자가 새 트랜잭션에 참여하기 전에 불확실한 트랜잭션을 모두 해결할 필요는 없습니다.첫 번째 단계는 리소스 관리자가 트랜잭션 관리자와 관계를 설정한 후 언제든지 수행할 수 있지만 <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>가 호출된 후\(2단계\)에는 1단계를 다시 수행할 수 없습니다.2단계는 트랜잭션의 결과에 영향을 주지 않고 여러 번 반복할 수 있습니다.