---
title: 연결 문자열 구문
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
caps.latest.revision: 11
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 76d8765be1dc24f4b8c457644595796680c2f2c3
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="connection-string-syntax"></a>연결 문자열 구문
각 .NET Framework 데이터 공급자에는 `Connection`뿐 아니라 공급자별 <xref:System.Data.Common.DbConnection> 속성에서 상속되는 <xref:System.Data.Common.DbConnection.ConnectionString%2A> 개체가 있습니다. 각 공급자의 특정 연결 문자열 구문은 해당 `ConnectionString` 속성에 설명되어 있습니다. 다음 표에서는 .NET Framework에 포함되어 있는 네 개의 데이터 공급자를 보여 줍니다.  
  
|.NET Framework 데이터 공급자(.NET Framework data provider)|설명|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|Microsoft SQL Server에 대한 데이터 액세스를 제공합니다. 연결 문자열 구문에 대한 자세한 내용은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>을 참조하세요.|  
|<xref:System.Data.OleDb>|OLE DB를 사용하여 노출되는 데이터 소스에 대한 데이터 액세스를 제공합니다. 연결 문자열 구문에 대한 자세한 내용은 <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>을 참조하세요.|  
|<xref:System.Data.Odbc>|ODBC를 사용하여 노출되는 데이터 소스에 대한 데이터 액세스를 제공합니다. 연결 문자열 구문에 대한 자세한 내용은 <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>을 참조하세요.|  
|<xref:System.Data.OracleClient>|Oracle 버전 8.1.7 이상에 대한 데이터 액세스를 제공합니다. 연결 문자열 구문에 대한 자세한 내용은 <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>을 참조하세요.|  
  
## <a name="connection-string-builders"></a>연결 문자열 작성기  
 ADO.NET 2.0에는 .NET Framework 데이터 공급자에 사용할 수 있는 다음과 같은 연결 문자열 작성기가 추가되었습니다.  
  
-   <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
-   <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
-   <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
-   <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 연결 문자열 작성기를 사용하면 구문이 올바른 연결 문자열을 런타임에 작성할 수 있기 때문에 코드에 연결 문자열 값을 직접 연결하지 않아도 됩니다. 자세한 내용은 참조 [연결 문자열 작성기](../../../../docs/framework/data/adonet/connection-string-builders.md)합니다.  

## <a name="windows-authentication"></a>Windows 인증  
 Windows 인증을 사용 하는 것이 좋습니다 (라고도 *통합 보안*)를 지 원하는 데이터 원본에 연결 합니다. 연결 문자열에 사용되는 구문은 공급자별로 다릅니다. 다음 표에서는 .NET Framework 데이터 공급자에서 사용되는 Windows 인증 구문을 보여 줍니다.  
  
|공급자|구문|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
>  `Integrated Security=true` 공급자와 함께 사용하는 경우 `OleDb`이면 예외가 throw됩니다.  
  
## <a name="sqlclient-connection-strings"></a>SqlClient 연결 문자열  
<xref:System.Data.SqlClient.SqlConnection> 연결 문자열의 구문은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> 속성에 설명되어 있습니다. <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> 속성을 사용하면 SQL Server 데이터베이스에 대한 연결 문자열을 가져오거나 설정할 수 있습니다. 이전 버전의 SQL Server에 연결해야 하는 경우에는 .NET Framework Data Provider for OleDb(<xref:System.Data.OleDb>)를 사용해야 합니다. 대부분의 연결 문자열 키워드는 또한 <xref:System.Data.SqlClient.SqlConnectionStringBuilder>의 속성에 매핑됩니다.  

> [!IMPORTANT]
>  에 대 한 기본 설정은 `Persist Security Info` 키워드는 `false`합니다. 이 키워드를 `true` 또는 `yes`로 설정하면 연결이 열린 다음 연결에서 사용자 ID 및 암호와 같은 보안 관련 정보를 얻을 수 있습니다. 유지 `Persist Security Info` 로 설정 `false` 하려면 신뢰할 수 없는 소스는 중요 한 연결 문자열 정보에 액세스할 수 없습니다.  

### <a name="windows-authentication-with-sqlclient"></a>SqlClient와 함께 Windows 인증 
 에 연결할 Windows 인증을 사용 하는 각각 다음과 같은 형태의 구문은 **AdventureWorks** 로컬 서버에는 데이터베이스입니다.  
  
```  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a>SqlClient와 함께 SQL Server 인증   
 SQL Server에 연결하기 위해 기본적으로 Windows 인증이 사용됩니다. 그러나 SQL Server 인증이 필요한 경우 다음 구문을 사용하여 사용자 이름과 암호를 지정하세요. 이 예제에서 유효한 사용자 이름과 암호를 나타내기 위해 별표를 사용합니다.  
  
```  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

Azure SQL 데이터 웨어하우스 또는 Azure SQL 데이터베이스에 연결 하 고 형식에서 로그인을 제공할 `user@servername`, 있는지 확인은 `servername` 로그인의 값에 제공 된 값이 일치 `Server=`합니다.

> [!NOTE]
>  Windows 인증은 SQL Server 로그인에 우선적으로 적용됩니다. Integrated Security=true와 사용자 이름 및 암호를 모두 지정하는 경우 사용자 이름과 암호는 무시되고 Windows 인증이 사용됩니다.  

### <a name="connect-to-a-named-instance-of-sql-server"></a>SQL Server의 명명 된 인스턴스에 연결
SQL Server의 명명된 된 인스턴스를 연결 하려면 사용 된 *서버 이름 \ 인스턴스 이름* 구문입니다.  
  
```  
Data Source=MySqlServer\MSSQL1;"  
```  
 
연결 문자열을 작성할 때 <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>의 `SqlConnectionStringBuilder` 속성을 인스턴스 이름으로 설정할 수도 있습니다. <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> 개체의 <xref:System.Data.SqlClient.SqlConnection> 속성은 읽기 전용입니다.  
  
### <a name="type-system-version-changes"></a>Type System Version 변경 내용  
 `Type System Version` 내의 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> 키워드는 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 형식의 클라이언트 측 표현을 지정합니다. <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> 키워드에 대한 자세한 내용은 `Type System Version`을 참조하세요.  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a>SQL Server Express 사용자 인스턴스에 연결 및 추가  
 사용자 인스턴스는 SQL Server Express의 한 기능입니다. 최소 권한의 로컬 Windows 계정에서 실행 중인 사용자가 관리자 권한 없이 SQL Server 데이터베이스에 연결하여 SQL Server 데이터베이스를 실행할 수 있습니다. 사용자 인스턴스는 서비스가 아닌 사용자의 Windows 자격 증명을 사용하여 실행됩니다.  
  
 사용자 인스턴스를 사용한 작업에 대 한 자세한 내용은 참조 하십시오. [SQL Server Express 사용자 인스턴스](../../../../docs/framework/data/adonet/sql/sql-server-express-user-instances.md)합니다.  
  
## <a name="using-trustservercertificate"></a>TrustServerCertificate 사용  
 `TrustServerCertificate` 키워드는 유효한 인증서로 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 인스턴스에 연결할 때만 유효합니다. `TrustServerCertificate`이 `true`로 설정된 경우 전송 계층에서는 SSL을 사용하여 채널을 암호화하고 인증서 체인을 무시하여 신뢰의 유효성을 확인합니다.  
  
```  
"TrustServerCertificate=true;"   
```  
  
> [!NOTE]
>  `TrustServerCertificate`이 `true`로 설정되고 암호화가 설정되면 연결 문자열에서 `Encrypt`가 `false`로 설정된 경우에도 서버에 지정된 암호화 수준이 사용됩니다. 그렇지 않으면 연결 문자열이 실패합니다.  
  
### <a name="enabling-encryption"></a>암호화 설정  
 인증서가 서버에서 제공 되지 경우 암호화를 사용 하는 **프로토콜 암호화 강제** 및 **서버 인증서 신뢰** 옵션은 SQL Server 구성 관리자에서 설정 되어야 합니다. 이 경우 확인 가능한 인증서가 서버에 제공되지 않은 경우 암호화에서 유효성 검사 없이 자체 서명한 서버 인증서를 사용합니다.  
  
 응용 프로그램 설정에서 SQL Server에 구성된 보안 수준을 낮출 수는 없지만 선택적으로 높일 수는 있습니다. 응용 프로그램을 설정 하 여 암호화를 요청할 수는 `TrustServerCertificate` 및 `Encrypt` 키워드를 `true`, 발생 하는 암호화 제공 된 서버 인증서가 있는 경우에 보장 및 **프로토콜 암호화 강제**  클라이언트에 대해 구성 되지 않았습니다. 그러나 `TrustServerCertificate`이 클라이언트 구성에서 설정되지 않은 경우 서버 인증서를 제공해야 합니다.  
  
 다음 표에는 가능한 모든 경우가 설명되어 있습니다.  
  
|프로토콜 암호화 강제 사용 클라이언트 설정|서버 인증서 신뢰 클라이언트 설정|데이터 연결 문자열/특성에 대해 암호화 및 암호화 사용|서버 인증서 신뢰 연결 문자열/특성|결과|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|아니요|N/A|아니요(기본값)|무시됨|암호화가 수행되지 않습니다.|  
|아니요|N/A|예|아니요(기본값)|확인 가능한 서버 인증서가 있으면 암호화가 설정되며 그렇지 않으면 연결이 실패합니다.|  
|아니요|N/A|예|예|확인 가능한 서버 인증서가 있으면 암호화가 설정되며 그렇지 않으면 연결이 실패합니다.|  
|예|아니요|무시됨|무시됨|확인 가능한 서버 인증서가 있으면 암호화가 설정되며 그렇지 않으면 연결이 실패합니다.|  
|예|예|아니요(기본값)|무시됨|확인 가능한 서버 인증서가 있으면 암호화가 설정되며 그렇지 않으면 연결이 실패합니다.|  
|예|예|예|아니요(기본값)|확인 가능한 서버 인증서가 있으면 암호화가 설정되며 그렇지 않으면 연결이 실패합니다.|  
|예|예|예|예|확인 가능한 서버 인증서가 있으면 암호화가 설정되며 그렇지 않으면 연결이 실패합니다.|  
  
 자세한 내용은 참조 [유효성 검사 없이 암호화를 사용 하 여](http://go.microsoft.com/fwlink/?LinkId=120500) SQL Server 온라인 설명서의 합니다.  
  
## <a name="oledb-connection-strings"></a>OleDb 연결 문자열  
 <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>의 <xref:System.Data.OleDb.OleDbConnection> 속성을 사용하면 Microsoft Access와 같은 OLE DB 데이터 소스에 대한 연결 문자열을 가져오거나 설정할 수 있습니다. `OleDb` 클래스를 사용하여 런타임에 <xref:System.Data.OleDb.OleDbConnectionStringBuilder> 연결 문자열을 만들 수도 있습니다.  
  
### <a name="oledb-connection-string-syntax"></a>OleDb 연결 문자열 구문  
 <xref:System.Data.OleDb.OleDbConnection> 연결 문자열의 공급자 이름을 지정해야 합니다. 다음 연결 문자열은 Jet 공급자를 사용하여 Microsoft Access 데이터베이스에 연결합니다. 데이터베이스가 보호되지 않는 경우(기본값) `UserID`와 `Password` 키워드를 선택적으로 사용할 수 있습니다.  
  
```  
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;   
```  
  
 사용자 수준의 보안을 사용하여 Jet 데이터베이스를 보호하는 경우에는 작업 그룹 정보 파일(.mdw)의 위치를 지정해야 합니다. 작업 그룹 정보 파일은 연결 문자열에 포함된 자격 증명의 유효성을 검사하는 데 사용됩니다.  
  
```  
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
>  에 대 한 연결 정보를 제공할 수는 **OleDbConnection** 유니버설 데이터 링크 (UDL) 파일입니다; 그러나 있습니다 이렇게 해서는 안 됩니다. UDL 파일은 암호화되지 않으므로 연결 문자열 정보를 일반 텍스트로 노출시킵니다. UDL 파일은 응용 프로그램에 대해 외부 파일 기반 리소스이므로 .NET Framework를 사용하여 보호할 수 없습니다. UDL 파일에 대 한 지원 되지 않습니다 **SqlClient**합니다.  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a>Access/Jet          DataDirectory     
 `DataDirectory`는 `SqlClient`와 같이 사용할 수 있습니다. 또한 <xref:System.Data.OleDb> 및 <xref:System.Data.Odbc> .NET 데이터 공급자와도 같이 사용할 수 있습니다. 다음 샘플 <xref:System.Data.OleDb.OleDbConnection> 문자열에서는 응용 프로그램의 app_data 폴더에 있는 Northwind.mdb에 연결하는 데 필요한 구문을 설명합니다. 시스템 데이터베이스(System.mdw)도 같은 위치에 저장됩니다.  
  
```  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
>  Access/Jet 데이터베이스가 안전하지 않은 경우 연결 문자열에 시스템 데이터베이스 위치를 지정할 필요가 없습니다. 기본적으로 보안이 해제되어 모든 사용자는 기본 제공 Admin 사용자 및 빈 암호로 연결됩니다. 사용자 수준 보안이 제대로 구현된 경우에도 Jet 데이터베이스는 공격에 취약합니다. 파일 기반 보안 스키마는 본래 보안에 취약하므로 Access/Jet 데이터베이스에 중요 정보를 저장하는 것은 권장되지 않습니다.  
  
### <a name="connecting-to-excel"></a>Excel에 연결  
 Microsoft Jet 공급자는 Excel 통합 문서에 연결하는 데 사용됩니다. 다음 연결 문자열에서 `Extended Properties` 키워드는 Excel 관련 속성을 설정합니다. "HDR=Yes;"는 첫 번째 행에 데이터가 아닌 열 이름이 있음을 나타내며 "IMEX=1;"은 "intermixed" 데이터 열을 항상 텍스트로 읽도록 드라이버에 지시합니다.  
  
```  
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 `Extended Properties`에 필요한 큰따옴표 문자는 큰따옴표로 묶어야 합니다.  
  
### <a name="data-shape-provider-connection-string-syntax"></a>Data Shape 공급자 연결 문자열 구문  
 Microsoft Data Shape 공급자를 사용하는 경우에는 `Provider`와 `Data Provider` 키워드를 모두 사용하세요. 다음 예제에서는 Data Shape 공급자를 사용하여 SQL Server의 로컬 인스턴스에 연결합니다.  
  
```  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"   
```  
  
## <a name="odbc-connection-strings"></a>Odbc 연결 문자열  
 <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>의 <xref:System.Data.Odbc.OdbcConnection> 속성을 사용하면 OLE DB 데이터 소스에 대한 연결 문자열을 가져오거나 설정할 수 있습니다. Odbc 연결 문자열은 <xref:System.Data.Odbc.OdbcConnectionStringBuilder>에서도 지원됩니다.  
  
 다음 연결 문자열에서는 Microsoft Text Driver를 사용합니다.  
  
```  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a>Visual FoxPro에 연결하기 위해 DataDirectory 사용  
 다음 <xref:System.Data.Odbc.OdbcConnection> 연결 문자열 샘플에서는 `DataDirectory`를 사용하여 Microsoft Visual FoxPro 파일에 연결하는 방법에 대해 설명합니다.  
  
```  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a>Oracle 연결 문자열  
 <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>의 <xref:System.Data.OracleClient.OracleConnection> 속성을 사용하면 OLE DB 데이터 소스에 대한 연결 문자열을 가져오거나 설정할 수 있습니다. Oracle 연결 문자열은 <xref:System.Data.OracleClient.OracleConnectionStringBuilder>에서도 지원됩니다.  
  
```  
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 ODBC 연결 문자열 구문에 대한 자세한 내용은 <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [연결 문자열](../../../../docs/framework/data/adonet/connection-strings.md)  
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
