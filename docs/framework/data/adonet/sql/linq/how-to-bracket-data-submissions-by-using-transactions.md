---
title: "방법: 트랜잭션을 사용하여 데이터 전송 표시 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: 트랜잭션을 사용하여 데이터 전송 표시
<xref:System.Transactions.TransactionScope>를 사용하여 데이터베이스에 대한 전송을 표시합니다.  자세한 내용은 [트랜잭션 지원](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)을 참조하세요.  
  
## 예제  
 다음 코드에서는 데이터베이스 전송을 <xref:System.Transactions.TransactionScope>로 묶습니다.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## 참고 항목  
 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [데이터 변경 및 변경 내용 전송](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [트랜잭션 지원](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)