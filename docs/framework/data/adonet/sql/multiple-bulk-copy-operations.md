---
title: "여러 개의 대량 복사 작업"
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
ms.assetid: 5ad12f94-7459-4a93-a421-4160d1a90715
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7db77dcd58e48927e8dac9bee82f7f14cdacf196
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="multiple-bulk-copy-operations"></a>여러 개의 대량 복사 작업
<xref:System.Data.SqlClient.SqlBulkCopy> 클래스의 단일 인스턴스를 사용하여 여러 대량 복사 작업을 수행할 수 있습니다. 작업 매개 변수 (예를 들어 대상 테이블의 이름) 복사본 간에 변경 하는 경우의 후속 호출 전에 업데이트 해야 하는 **WriteToServer** 메서드를 다음 예제와 같이 합니다. 명시적으로 변경하지 않는 한 모든 속성 값은 지정된 인스턴스에 대한 이전의 대량 복사 작업과 동일하게 유지됩니다.  
  
> [!NOTE]
>  <xref:System.Data.SqlClient.SqlBulkCopy>의 단일 인스턴스를 사용하여 여러 대량 복사 작업을 수행하는 것은 작업마다 별도의 인스턴스를 사용하는 방법보다 대개 효율적입니다.  
  
 동일한 <xref:System.Data.SqlClient.SqlBulkCopy> 개체를 사용하여 여러 대량 복사 작업을 수행하는 경우 각 작업에서 소스 또는 대상 정보가 동일한지 여부에 대한 제한이 없습니다. 그러나 열 연결 정보는 서버에 쓸 때마다 올바르게 설정되어 있어야 합니다.  
  
> [!IMPORTANT]
>  이 샘플을 만들지 않은 경우 작업 테이블에 설명 된 대로 실행 되지 것입니다 [대량 복사 예제 설정](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md)합니다. 이 코드는 사용 하는 구문을 보여 주기 위해 제공 됩니다 **SqlBulkCopy** 만 합니다. 소스 테이블과 대상 테이블이 동일한 SQL Server 인스턴스에 있으면 Transact-SQL `INSERT … SELECT` 문을 사용하여 데이터를 더 쉽고 빠르게 복사할 수 있습니다.  
  
 [!code-csharp[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/CS/source.cs#1)]
 [!code-vb[DataWorks SqlBulkCopy.ColumnMappingOrdersDetails#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlBulkCopy.ColumnMappingOrdersDetails/VB/source.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [SQL Server의 대량 복사 작업](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
