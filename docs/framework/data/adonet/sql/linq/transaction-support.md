---
title: "트랜잭션 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 트랜잭션 지원
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 세 개의 고유한 트랜잭션 모델이 지원됩니다.  이러한 모델을 검사가 수행되는 순서대로 나열하면 다음과 같습니다.  
  
## 명시적 로컬 트랜잭션  
 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>가 호출될 때 <xref:System.Data.Linq.DataContext.Transaction%2A> 속성이 \(`IDbTransaction`\) 트랜잭션으로 설정된 경우 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 호출은 동일한 트랜잭션의 컨텍스트에서 실행됩니다.  
  
 트랜잭션이 성공적으로 실행된 후 트랜잭션을 커밋하거나 롤백하는 작업은 직접 수행해야 합니다.  트랜잭션에 해당하는 연결은 <xref:System.Data.Linq.DataContext>를 생성하는 데 사용되는 연결과 일치해야 합니다.  다른 연결이 사용될 경우 예외가 throw됩니다.  
  
## 명시적 배포 가능 트랜잭션  
 활성 <xref:System.Transactions.Transaction>의 범위에서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] API\(<xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 포함하지만 여기에 제한되지는 않음\)를 호출할 수 있습니다.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 호출이 트랜잭션 범위에 있음을 감지하고 새 트랜잭션을 만들지 않습니다.  또한 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 이 경우 연결이 닫히지 않도록 조치합니다.  이러한 트랜잭션의 컨텍스트에서 쿼리 및 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 실행을 수행할 수 있습니다.  
  
## 암시적 트랜잭션  
 <xref:System.Data.Linq.DataContext.SubmitChanges%2A>를 호출할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 호출이 <xref:System.Transactions.Transaction>의 범위에 있는지 또는 `Transaction` 속성\(`IDbTransaction`\)이 사용자가 시작한 로컬 트랜잭션으로 설정되었는지 여부를 확인합니다.  어떠한 트랜잭션도 찾지 못한 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 로컬 트랜잭션\(`IDbTransaction`\)을 시작하고 이를 사용하여 생성된 SQL 명령을 실행합니다.  모든 SQL 명령이 성공적으로 완료되면 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 로컬 트랜잭션을 커밋하고 반환됩니다.  
  
## 참고 항목  
 [배경 정보](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [방법: 트랜잭션을 사용하여 데이터 전송 표시](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)