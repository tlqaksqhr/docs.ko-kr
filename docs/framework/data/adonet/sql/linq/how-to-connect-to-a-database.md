---
title: "방법: 데이터베이스의 데이터에 연결"
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
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: d03dc5a3775ee9396573d58637c32f824760768f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-connect-to-a-database"></a>방법: 데이터베이스의 데이터에 연결
<xref:System.Data.Linq.DataContext>는 데이터베이스에 연결하여 개체를 검색하고 변경 내용을 데이터베이스로 다시 전송하는 주 통로입니다. <xref:System.Data.Linq.DataContext> [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]을 사용하는 것처럼 <xref:System.Data.SqlClient.SqlConnection>를 사용합니다. 실제로 <xref:System.Data.Linq.DataContext>는 사용자가 지정한 연결 또는 연결 문자열을 통해 초기화됩니다. 자세한 내용은 참조 [DataContext 메서드 (O/R 디자이너)](/visualstudio/data-tools/datacontext-methods-o-r-designer)합니다.  
  
 <xref:System.Data.Linq.DataContext>의 용도는 개체에 대한 요청을 데이터베이스에 적용할 수 있는 SQL 쿼리로 변환한 다음 결과 외의 개체를 어셈블하는 것입니다. <xref:System.Data.Linq.DataContext>에서는 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] 및 `Where` 등의 표준 쿼리 연산자와 같은 동일한 연산자 패턴을 구현하여 `Select`를 사용할 수 있습니다.  
  
> [!IMPORTANT]
>  보안 연결을 유지 관리하는 것이 가장 중요합니다. 자세한 내용은 참조 [linq to SQL 보안](../../../../../../docs/framework/data/adonet/sql/linq/security-in-linq-to-sql.md)합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.Data.Linq.DataContext>를 사용하여 Northwind 샘플 데이터베이스에 연결한 다음 도시가 London인 고객의 행을 검색합니다.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 각 데이터베이스 테이블은 해당 테이블을 식별할 수 있는 엔터티 클래스를 사용하여 `Table` 메서드를 통해 사용할 수 있는 <xref:System.Data.Linq.DataContext.GetTable%2A> 컬렉션으로 나타납니다.  
  
## <a name="example"></a>예  
 가장 좋은 방법은 기본 <xref:System.Data.Linq.DataContext> 클래스와 <xref:System.Data.Linq.DataContext> 메서드를 사용하는 대신 강력한 형식의 <xref:System.Data.Linq.DataContext.GetTable%2A>를 선언하는 것입니다. 강력한 형식의 <xref:System.Data.Linq.DataContext>에서는 다음 예제와 같이 `Table` 컬렉션을 컨텍스트의 멤버로 선언합니다.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 그런 다음 London에 있는 고객에 대한 쿼리를 다음과 같이 더 간단하게 표현할 수 있습니다.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터베이스와 통신](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
