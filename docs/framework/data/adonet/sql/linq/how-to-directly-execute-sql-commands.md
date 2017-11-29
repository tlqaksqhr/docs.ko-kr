---
title: "방법: SQL 명령 직접 실행"
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
ms.assetid: 04671bb0-40c0-4465-86e5-77986f454661
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: feffa98fa890856db579553df6624fef1897b173
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-directly-execute-sql-commands"></a>방법: SQL 명령 직접 실행
<xref:System.Data.Linq.DataContext> 연결에서는 <xref:System.Data.Linq.DataContext.ExecuteCommand%2A>를 사용하여 개체를 반환하지 않는 SQL 명령을 실행할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 SQL 서버에서 UnitPrice를 1.00만큼 증가시키는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#3)]
 [!code-vb[DLinqCommunicatingWithDatabase#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: SQL 쿼리 직접 실행](../../../../../../docs/framework/data/adonet/sql/linq/how-to-directly-execute-sql-queries.md)  
 [데이터베이스와 통신](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
