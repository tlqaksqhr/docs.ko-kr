---
title: "저장 프로시저로 데이터 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d8e9a46-1af6-4a02-bf61-969d77ae07e0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 저장 프로시저로 데이터 수정
저장 프로시저는 입력 매개 변수로 데이터를 받아들이고 출력 매개 변수, 결과 집합 또는 반환 값으로 데이터를 반환할 수 있습니다.  다음 샘플에서는 ADO.NET에서 입력 매개 변수, 출력 매개 변수 및 반환 값을 보내고 받는 방법을 보여 줍니다.  이 예제에서는 기본 키 열이 SQL Server 데이터베이스의 ID 열인 테이블에 새 레코드를 삽입합니다.  
  
> [!NOTE]
>  SQL Server 저장 프로시저를 통해 <xref:System.Data.SqlClient.SqlDataAdapter>로 데이터를 편집하거나 삭제하는 경우에는 저장 프로시저 정의에 SET NOCOUNT ON을 사용하면 안 됩니다.  SET NOCOUNT ON을 사용하는 경우 반환되는 행 개수가 0이 되어 `DataAdapter`가 이를 동시성 충돌로 인식합니다.  그 결과 <xref:System.Data.DBConcurrencyException>이 throw됩니다.  
  
## 예제  
 이 샘플에서는 다음 저장 프로시저를 사용하여 **Northwind** **Categories** 테이블에 새 범주를 삽입합니다.  저장 프로시저에서는 **CategoryName** 열의 값을 입력 매개 변수로 받아 SCOPE\_IDENTITY\(\) 함수를 사용하여 ID 필드인 **CategoryID**의 새 값을 검색한 다음 이를 출력 매개 변수로 반환합니다.  RETURN 문에서는 @@ROWCOUNT 함수를 사용하여 삽입된 행의 수를 반환합니다.  
  
```  
CREATE PROCEDURE dbo.InsertCategory  
  @CategoryName nvarchar(15),  
  @Identity int OUT  
AS  
INSERT INTO Categories (CategoryName) VALUES(@CategoryName)  
SET @Identity = SCOPE_IDENTITY()  
RETURN @@ROWCOUNT  
```  
  
 다음 코드 예제에서는 위의 `InsertCategory` 저장 프로시저를 <xref:System.Data.SqlClient.SqlDataAdapter>의 <xref:System.Data.SqlClient.SqlDataAdapter.InsertCommand%2A>에 대한 소스로 사용합니다.  <xref:System.Data.SqlClient.SqlDataAdapter>의 `Update` 메서드를 호출하면 데이터베이스에 레코드가 삽입된 후 `@Identity` 출력 매개 변수가 <xref:System.Data.DataSet>에 반영됩니다.  이 코드는 반환 값도 검색합니다.  
  
> [!NOTE]
>  <xref:System.Data.OleDb.OleDbDataAdapter>를 사용하는 경우 **ReturnValue**의 <xref:System.Data.ParameterDirection>을 사용하는 매개 변수를 다른 매개 변수 앞에 지정해야 합니다.  
  
 [!code-csharp[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/CS/source.cs#1)]
 [!code-vb[DataWorks SqlClient.SprocIdentityReturn#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlClient.SprocIdentityReturn/VB/source.vb#1)]  
  
## 참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [DataAdapters 및 DataReaders](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)   
 [명령 실행](../../../../docs/framework/data/adonet/executing-a-command.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)