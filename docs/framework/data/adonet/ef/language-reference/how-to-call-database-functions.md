---
title: "방법: 데이터베이스 함수 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 4395128abc3a8f604eee762479bc1a26bed7f95b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-call-database-functions"></a>방법: 데이터베이스 함수 호출
<xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스에는 LINQ to Entities 쿼리에 사용할 SQL Server 함수를 노출하는 메서드가 포함되어 있습니다. LINQ to Entities 쿼리에서 <xref:System.Data.Objects.SqlClient.SqlFunctions> 메서드를 사용할 때 해당되는 데이터베이스 함수가 데이터베이스에서 실행됩니다.  
  
> [!NOTE]
>  값 집합에 대한 계산을 수행하고 집계 데이터베이스 함수라고도 하는 단일 값을 반환하는 데이터베이스 함수를 직접 호출할 수 있습니다. 기타 정식 함수는 LINQ to Entities 쿼리의 일부로만 호출할 수 있습니다. 집계 함수를 직접 호출하려면 <xref:System.Data.Objects.ObjectQuery%601>를 함수로 전달해야 합니다. 자세한 내용은 아래 두 번째 예제를 참조하세요.  
  
> [!NOTE]
>  <xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스의 메서드는 SQL Server 함수와 관련되어 있습니다. 데이터베이스 함수를 노출하는 유사한 클래스가 다른 공급자를 통해 제공될 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)합니다. 이 예제에서는 <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> 메서드를 사용하여 성이 "Si"로 시작하는 모든 담당자를 반환하는 LINQ to Entities 쿼리를 실행합니다.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>예  
 다음 예제에서는 [AdventureWorks Sales 모델](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832)합니다. 이 예제에서는 집계 <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> 메서드를 직접 호출합니다. <xref:System.Data.Objects.ObjectQuery%601>는 LINQ to Entities 쿼리에 포함되지 않고 호출되도록 지정하는 함수로 전달됩니다.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Entities 쿼리에서 함수 호출](../../../../../../docs/framework/data/adonet/ef/language-reference/calling-functions-in-linq-to-entities-queries.md)  
 [LINQ to Entities에서 쿼리](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
