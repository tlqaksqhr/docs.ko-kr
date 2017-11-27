---
title: "방법: 생성된 SQL 표시"
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
ms.assetid: 626492c0-5ee3-4675-88e8-8c40379510b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 523a6cbd0174da4c294e5fd2ab2d0217fc63cb5c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-display-generated-sql"></a>방법: 생성된 SQL 표시
<xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 쿼리에 대해 생성된 SQL 코드를 보고 프로세스를 변경할 수 있습니다. 이러한 접근 방식은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기능을 이해하고 특정 문제를 디버깅하는 데 유용합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Linq.DataContext.Log%2A> 속성을 사용하여 코드를 실행하기 전에 콘솔 창에 SQL 코드를 표시합니다.  이 속성은 쿼리, 삽입, 업데이트 및 삭제 명령과 함께 사용할 수 있습니다.  
  
 콘솔 창의 줄은 다음 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 또는 C# 코드를 실행할 때 표시됩니다.  
  
```  
SELECT [t0].[CustomerID], [t0].[CompanyName], [t0].[ContactName], [t0].[ContactT  
itle], [t0].[Address], [t0].[City], [t0].[Region], [t0].[PostalCode], [t0].[Coun  
try], [t0].[Phone], [t0].[Fax]  
FROM [dbo].[Customers] AS [t0]  
WHERE [t0].[City] = @p0  
-- @p0: Input String (Size = 6; Prec = 0; Scale = 0) [London]  
-- Context: SqlProvider(Sql2005) Model: AttributedMetaModel Build: 3.5.20810.0  
```  
  
```  
AROUT  
BSBEV  
CONSH  
EASTC  
NORTS  
SEVES  
```  
  
 [!code-csharp[DLinqDebuggingSupport#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDebuggingSupport/cs/Program.cs#1)]
 [!code-vb[DLinqDebuggingSupport#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDebuggingSupport/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [디버깅 지원](../../../../../../docs/framework/data/adonet/sql/linq/debugging-support.md)
