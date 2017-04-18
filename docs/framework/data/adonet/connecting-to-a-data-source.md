---
title: "데이터 원본에 연결(ADO.NET) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 데이터 원본에 연결(ADO.NET)
ADO.NET에서는 연결 문자열에 필요한 인증 정보를 제공함으로써 **Connection** 개체를 사용하여 특정 데이터 소스에 연결합니다.  사용하는 **Connection** 개체는 데이터 소스의 형식에 따라 다릅니다.  
  
 .NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.  
  
## 단원 내용  
 [연결 설정](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 **Connection** 개체를 사용하여 데이터 소스에 대한 연결을 설정하는 방법을 설명합니다.  
  
 [연결 이벤트](../../../../docs/framework/data/adonet/connection-events.md)  
 **InfoMessage** 이벤트를 사용하여 데이터 소스에서 정보 메시지를 검색하는 방법을 설명합니다.  
  
## 참고 항목  
 [연결 문자열](../../../../docs/framework/data/adonet/connection-strings.md)   
 [연결 풀링](../../../../docs/framework/data/adonet/connection-pooling.md)   
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [DataAdapters 및 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)