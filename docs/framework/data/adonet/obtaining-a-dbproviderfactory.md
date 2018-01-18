---
title: "DbProviderFactory 가져오기"
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
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a018447b790dde047bd76e1319a13aa3f77ffc61
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="obtaining-a-dbproviderfactory"></a>DbProviderFactory 가져오기
<xref:System.Data.Common.DbProviderFactory>를 가져오는 프로세스에서는 데이터 공급자에 대한 정보가 <xref:System.Data.Common.DbProviderFactories> 클래스에 전달됩니다. <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> 메서드는 이 정보를 기반으로 하여 강력한 형식의 공급자 팩터리를 만듭니다. 예를 들어 <xref:System.Data.SqlClient.SqlClientFactory>를 만들려면 공급자 이름을 "System.Data.SqlClient"로 지정하는 문자열을 `GetFactory`에 전달합니다. `GetFactory`의 다른 오버로드는 <xref:System.Data.DataRow>를 사용합니다. 공급자 팩터리를 만든 후에는 해당 메서드를 사용하여 다른 개체를 만들 수 있습니다. `SqlClientFactory`의 메서드로는 <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> 및 <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>가 있습니다.  
  
> [!NOTE]
>  .NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> 및 <xref:System.Data.OleDb.OleDbFactory> 클래스도 이와 유사한 기능을 제공합니다.  
  
## <a name="registering-dbproviderfactories"></a>DbProviderFactories 등록  
 팩터리 기반의 클래스를 지 원하는 각.NET Framework 데이터 공급자에 대 한 구성 정보를 등록는 **DbProviderFactories** 의 섹션은 **machine.config** 로컬 컴퓨터의 파일입니다. 다음 구성 파일 조각에서는 <xref:System.Data.SqlClient>의 구문과 형식을 보여 줍니다.  
  
```xml  
<system.data>  
  <DbProviderFactories>  
    <add name="SqlClient Data Provider"  
     invariant="System.Data.SqlClient"   
     description=".Net Framework Data Provider for SqlServer"   
     type="System.Data.SqlClient.SqlClientFactory, System.Data,   
     Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
    />  
  </DbProviderFactories>  
</system.data>  
```  
  
 **고정** 특성 기본 데이터 공급자를 식별 합니다. 세 부분으로 이루어진 이 명명 구문은 새 팩터리를 만들 때뿐만 아니라 공급자 이름 및 관련된 연결 문자열을 런타임에 검색할 수 있도록 응용 프로그램 구성 파일에서 공급자를 식별하는 데도 사용됩니다.  
  
## <a name="retrieving-provider-information"></a>공급자 정보 검색  
 <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> 메서드를 사용하면 로컬 컴퓨터에 설치되어 있는 데이터 공급자에 대한 모든 정보를 검색할 수 있습니다. 반환 된 <xref:System.Data.DataTable> 라는 **DbProviderFactories** 다음 표에 설명 된 열을 포함 하 합니다.  
  
|열 서수|열 이름|예제 출력|설명|  
|--------------------|-----------------|--------------------|-----------------|  
|0|**이름**|SqlClient Data Provider|읽을 수 있는 데이터 공급자 이름|  
|1|**설명**|.Net Framework Data Provider for SqlServer|읽을 수 있는 데이터 공급자 설명|  
|2|**InvariantName**|System.Data.SqlClient|데이터 공급자를 프로그래밍 방식으로 참조하는 데 사용할 수 있는 이름|  
|3|**AssemblyQualifiedName**|System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089|개체를 인스턴스화하는 데 충분한 정보가 포함된 팩터리 클래스의 정규화된 이름|  
  
 이 `DataTable`을 사용하면 런타임에 사용자가 <xref:System.Data.DataRow>를 선택할 수 있습니다. 그런 다음 선택한 `DataRow`를 <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> 메서드에 전달하여 강력한 형식의 <xref:System.Data.Common.DbProviderFactory>를 만들 수 있습니다. 선택한 <xref:System.Data.DataRow>를 `GetFactory` 메서드에 전달하면 원하는 `DbProviderFactory` 개체를 만들 수 있습니다.  
  
## <a name="listing-the-installed-provider-factory-classes"></a>설치되어 있는 공급자 팩터리 클래스 나열  
 이 예제에서는 <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> 메서드를 사용하여 설치되어 있는 공급자에 대한 정보가 포함된 <xref:System.Data.DataTable>을 반환하는 방법을 설명합니다. 이 코드는 `DataTable`의 각 행을 반복하여 현재 설치되어 있는 각 공급자에 대한 정보를 콘솔 창에 표시합니다.  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## <a name="using-application-configuration-files-to-store-factory-information"></a>응용 프로그램 구성 파일을 사용하여 팩터리 정보 저장  
 팩터리로 작업에 사용 되는 디자인 패턴와 같은 응용 프로그램 구성 파일에서 공급자 및 연결 문자열 정보를 저장 하는 과정이 수반 됩니다 **app.config** Windows 응용 프로그램에 대 한 및 **web.config**  ASP.NET 응용 프로그램에 대 한 합니다.  
  
 다음 구성 파일 조각에서는 SQL Server에서 Northwind 데이터베이스에 연결하는 데 필요한 "NorthwindSQL" 및 Access/Jet에서 Northwind 데이터베이스에 연결하는 데 필요한 "NorthwindAccess"라는 두 가지 명명된 연결 문자열을 저장하는 방법을 보여 줍니다. **고정** 이름에 사용 되는 **providerName** 특성입니다.  
  
```xml  
<configuration>  
  <connectionStrings>  
    <clear/>  
    <add name="NorthwindSQL"   
     providerName="System.Data.SqlClient"   
     connectionString=  
     "Data Source=MSSQL1;Initial Catalog=Northwind;Integrated Security=true"  
    />  
  
    <add name="NorthwindAccess"   
     providerName="System.Data.OleDb"   
     connectionString=  
     "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Data\Northwind.mdb;"  
    />  
  </connectionStrings>  
</configuration>  
```  
  
### <a name="retrieving-a-connection-string-by-provider-name"></a>공급자 이름을 사용하여 연결 문자열 검색  
 공급자 팩터리를 만들려면 연결 문자열뿐만 아니라 공급자 이름도 제공해야 합니다. 고정 형식으로 공급자 이름을 전달 하 여 응용 프로그램 구성 파일에서 연결 문자열을 검색 하는 방법을 보여 주는이 예제 "*System.Data.ProviderName*"입니다. 이 코드는 <xref:System.Configuration.ConnectionStringSettingsCollection>을 반복합니다. 메서드가 성공하면 <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>이 반환되고, 그렇지 않으면 `null`(Visual Basic의 경우에는 `Nothing`)이 반환됩니다. 공급자에 대한 항목이 여러 개 있으면 응용 프로그램 구성 파일에서 찾은 첫 번째 항목이 반환됩니다. 자세한 내용과 예제 구성 파일에서 연결 문자열을 검색 하는 참조 [연결 문자열 및 구성 파일](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md)합니다.  
  
> [!NOTE]
>  코드를 실행하려면 `System.Configuration.dll`에 대한 참조가 필요합니다.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a>DbProviderFactory 및 DbConnection 만들기  
 만드는 방법을 보여 주는이 예제는 <xref:System.Data.Common.DbProviderFactory> 및 <xref:System.Data.Common.DbConnection> 형식에서 공급자 이름을 전달 하 여 "*System.Data.ProviderName*" 및 연결 문자열입니다. 메서드가 성공하면 `DbConnection` 개체가 반환되고, 오류가 발생하면 `null` (Visual Basic의 경우에는 `Nothing`)이 반환됩니다.  
  
 이 코드는 `DbProviderFactory`를 호출하여 <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>를 가져옵니다. 그러면 <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> 메서드가 <xref:System.Data.Common.DbConnection> 개체를 만들고 <xref:System.Data.Common.DbConnection.ConnectionString%2A> 속성이 연결 문자열에 설정됩니다.  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [연결 문자열](../../../../docs/framework/data/adonet/connection-strings.md)  
 [구성 클래스를 사용 하 여](http://msdn.microsoft.com/library/98d2b386-baf6-4a17-974b-76e3b4c87acc)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
