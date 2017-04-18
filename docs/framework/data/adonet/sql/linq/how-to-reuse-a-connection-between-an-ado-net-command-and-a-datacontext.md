---
title: "방법: ADO.NET 명령과 DataContext 간의 연결 다시 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 방법: ADO.NET 명령과 DataContext 간의 연결 다시 사용
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 제품군 기술의 일부이고 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]에서 제공하는 서비스를 기반으로 하기 때문에 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령과 <xref:System.Data.Linq.DataContext> 간의 연결을 다시 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령과 <xref:System.Data.Linq.DataContext> 간에 동일한 연결을 다시 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## 참고 항목  
 [배경 정보](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [ADO.NET 및 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)   
 [데이터베이스와 통신](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)