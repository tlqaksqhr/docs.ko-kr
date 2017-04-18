---
title: "DbDataAdapter로 데이터 수정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e35c7f9e-648b-4fcc-9361-d365c3e42c9a
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DbDataAdapter로 데이터 수정
<xref:System.Data.Common.DbProviderFactory> 개체의 <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> 메서드를 사용하면 팩터리를 만들 때 지정한 기본 데이터 공급자에 대해 강력한 형식의 <xref:System.Data.Common.DbDataAdapter> 개체를 얻을 수 있습니다.  그런 다음 <xref:System.Data.Common.DbCommandBuilder>를 사용하여 데이터를 <xref:System.Data.DataSet>에서 데이터 소스로 삽입하고, 업데이트하고, 삭제하는 명령을 만들 수 있습니다.  
  
## DbDataAdapter를 사용하여 데이터 검색  
 이 예제에서는 공급자 이름과 연결 문자열을 기반으로 강력한 형식의 `DbDataAdapter`를 만드는 방법을 보여 줍니다.  이 코드에서는 <xref:System.Data.Common.DbProviderFactory>의 <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> 메서드를 사용하여 <xref:System.Data.Common.DbConnection>을 만듭니다.  그런 다음 <xref:System.Data.Common.DbProviderFactory.CreateCommand%2A> 메서드를 사용하고 `CommandText` 및 `Connection` 속성을 설정하여 데이터를 선택하기 위한 <xref:System.Data.Common.DbCommand>를 만듭니다.  마지막으로, <xref:System.Data.Common.DbProviderFactory.CreateDataAdapter%2A> 메서드를 사용하여 <xref:System.Data.Common.DbDataAdapter> 개체를 만들고 해당 `SelectCommand` 속성을 설정합니다.  `DbDataAdapter`의 `Fill` 메서드는 데이터를 <xref:System.Data.DataTable>로 로드합니다.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapter#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapter/VB/source.vb#1)]  
  
## DbDataAdapter로 데이터 수정  
 이 예제에서는 <xref:System.Data.Common.DbCommandBuilder>를 사용하여 데이터 소스의 데이터를 업데이트하는 데 필요한 명령을 생성함으로써 <xref:System.Data.Common.DbDataAdapter>를 사용하여 `DataTable`의 데이터를 수정하는 방법을 보여 줍니다.  `DbDataAdapter`의 <xref:System.Data.Common.DbDataAdapter.SelectCommand%2A>를 설정하여 Customers 테이블에서 CustomerID 및 CompanyName을 검색합니다.  <xref:System.Data.Common.DbCommandBuilder.GetInsertCommand%2A> 메서드는 <xref:System.Data.Common.DbDataAdapter.InsertCommand%2A> 속성을 설정하는 데 사용되고, <xref:System.Data.Common.DbCommandBuilder.GetUpdateCommand%2A> 메서드는 <xref:System.Data.Common.DbDataAdapter.UpdateCommand%2A> 속성을 설정하는 데 사용되고, <xref:System.Data.Common.DbCommandBuilder.GetDeleteCommand%2A> 메서드는 <xref:System.Data.Common.DbDataAdapter.DeleteCommand%2A> 속성을 설정하는 데 사용됩니다.  코드에서는 Customers 테이블에 새 행을 추가하고 데이터 소스를 업데이트합니다.  그런 다음 Customers 테이블에 대해 정의된 기본 키인 CustomerID를 검색하여 추가된 행을 찾습니다.  그런 후 CompanyName을 변경하고 데이터 소스를 업데이트합니다.  마지막으로 행을 삭제합니다.  
  
 [!code-csharp[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.DbDataAdapterModify#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.DbDataAdapterModify/VB/source.vb#1)]  
  
## 매개 변수 처리  
 .NET Framework 데이터 공급자는 매개 변수와 매개 변수 자리 표시자를 다르게 지정하여 명명 작업을 처리합니다.  이 구문은 다음 표에서 설명하는 것과 같이 특정 데이터 소스에 맞게 수정됩니다.  
  
|데이터 공급자|매개 변수 명명 구문|  
|-------------|-----------------|  
|`SqlClient`|`@` *parametername* 형식의 명명된 매개 변수를 사용합니다.|  
|`OracleClient`|`:` *parmname*\(또는 *parmname*\) 형식의 명명된 매개 변수를 사용합니다.|  
|`OleDb`|물음표\(`?`\)로 표시된 위치 매개 변수 마커를 사용합니다.|  
|`Odbc`|물음표\(`?`\)로 표시된 위치 매개 변수 마커를 사용합니다.|  
  
 팩터리 모델은 매개 변수화된 `DbCommand` 및 `DbDataAdapter` 개체를 만들 때는 유용하지 않습니다.  코드에서 분기하여 데이터 공급자에 맞는 매개 변수를 만들어야 합니다.  
  
> [!IMPORTANT]
>  문자열 연결을 사용하여 직접 SQL 문을 구성함으로써 공급자 특정 매개 변수를 사용하지 않는 것은 보안상 권장하지 않습니다.  매개 변수 대신 문자열 연결을 사용하면 응용 프로그램이 SQL 삽입 공격에 취약해집니다.  
  
## 참고 항목  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)   
 [DbProviderFactory 가져오기](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)   
 [DbConnection, DbCommand 및 DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)