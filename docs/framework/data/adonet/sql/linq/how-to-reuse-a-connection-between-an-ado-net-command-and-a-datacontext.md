---
title: "방법: ADO.NET 명령 및 DataContext 사이에 연결 다시 사용"
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
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 483a97817162140af61df6a58c3e9ab003235c74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>방법: ADO.NET 명령 및 DataContext 사이에 연결 다시 사용
때문에 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 의 일부인는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 기술 제품군의 제공 하는 서비스를 기반으로 하 고 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], 사이의 연결을 다시 사용할 수는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령 및 <xref:System.Data.Linq.DataContext>합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 명령과 <xref:System.Data.Linq.DataContext> 간에 동일한 연결을 다시 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [배경 정보](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [ADO.NET 및 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [데이터베이스와 통신](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
