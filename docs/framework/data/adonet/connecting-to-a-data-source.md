---
title: "데이터 원본에 연결(ADO.NET)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0d21c571b659e9d7aef65893db18b034d614e2af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="connecting-to-a-data-source-in-adonet"></a>데이터 원본에 연결(ADO.NET)
ADO.NET에서 사용 하는 **연결** 개체에 연결 문자열에 필요한 인증 정보를 제공 하 여 특정 데이터 원본에 연결 합니다. **연결** 개체를 사용 하면 데이터 원본의 유형에 따라 다릅니다.  
  
 .NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [연결 설정](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 사용 하는 방법에 설명 된 **연결** 데이터 원본에 대 한 연결을 설정 하기 위해 개체입니다.  
  
 [연결 이벤트](../../../../docs/framework/data/adonet/connection-events.md)  
 사용 하는 방법에 설명 된 **InfoMessage** 이벤트를 데이터 원본에서 정보 메시지를 검색 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연결 문자열](../../../../docs/framework/data/adonet/connection-strings.md)  
 [연결 풀링](../../../../docs/framework/data/adonet/connection-pooling.md)  
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Dataadapter 및 Datareader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
