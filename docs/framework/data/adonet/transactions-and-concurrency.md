---
title: "트랜잭션 및 동시성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6e6dfa946313bb9d43077bad68b761e8f03c175c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="transactions-and-concurrency"></a>트랜잭션 및 동시성
트랜잭션은 패키지로 실행되는 하나의 명령 또는 명령 그룹으로 구성됩니다. 트랜잭션을 사용하여 여러 작업을 하나의 작업 단위로 통합할 수 있습니다. 또한 트랜잭션의 한 지점에서 오류가 발생하는 경우 모든 업데이트를 이전 트랜잭션 상태로 롤백할 수 있습니다.  
  
 트랜잭션은 데이터 일관성을 유지하기 위해 Atomicity(원자성), Consistency(일관성), Isolation(격리성) 및 Durability(영속성)를 나타내는 ACID 속성을 따라야 합니다. Microsoft SQL Server 같은 대부분의 관계형 데이터베이스 시스템에서는 클라이언트 응용 프로그램이 작업을 업데이트, 삽입 또는 삭제할 때마다 잠금, 로깅 및 트랜잭션 관리 기능을 제공하여 트랜잭션을 지원합니다.  
  
> [!NOTE]
>  잠금이 너무 길게 유지되면 트랜잭션에 여러 리소스가 관여하는 경우 동시성이 낮아질 수 있습니다. 따라서 트랜잭션은 가능한 한 짧게 유지하세요.  
  
 같은 데이터베이스나 서버에 여러 테이블이 있는 트랜잭션의 경우에는 저장 프로시저의 명시적 트랜잭션이 더 효과적으로 수행되는 경우가 많습니다. SQL Server 저장 프로시저에서는 Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` 및 `ROLLBACK TRANSACTION` 문을 사용하여 트랜잭션을 만들 수 있습니다. 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.  
  
 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]과 Oracle 간의 트랜잭션 같은 여러 리소스 관리자가 관련된 트랜잭션에는 분산 트랜잭션이 필요합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [로컬 트랜잭션](../../../../docs/framework/data/adonet/local-transactions.md)  
 데이터베이스에 대해 트랜잭션을 수행하는 방법을 설명합니다.  
  
 [분산 트랜잭션](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 ADO.NET에서 분산 트랜잭션을 수행하는 방법을 설명합니다.  
  
 [SQL Server와의 System.Transactions 통합](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 분산 트랜잭션 작업을 위한 <xref:System.Transactions>과 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]의 통합에 대해 설명합니다.  
  
 [낙관적 동시성](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 낙관적 및 비관적 동시성에 대해 설명하고 동시성 위반을 테스트하는 방법에 대해 살펴봅니다.  
  
## <a name="see-also"></a>참고 항목  
 [트랜잭션 기본 사항](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [DataAdapter 및 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
