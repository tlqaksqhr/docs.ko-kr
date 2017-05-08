---
title: "ADO.NET에서의 Side-by-Side 실행 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# ADO.NET에서의 Side-by-Side 실행
[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서의 side\-by\-side 실행은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 여러 버전이 설치되어 있는 컴퓨터에서 응용 프로그램을 컴파일한 버전만 사용하여 응용 프로그램을 실행하는 기능입니다.  side\-by\-side 실행을 구성하는 방법에 대한 자세한 내용은 [Side\-by\-Side 실행](../../../../docs/framework/deployment/side-by-side-execution.md)을 참조하세요.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 특정 버전을 사용하여 컴파일된 응용 프로그램을 다른 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서 실행할 수 있습니다.  그러나 설치되어 있는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 버전별로 응용 프로그램 버전을 컴파일하여 개별적으로 실행하는 것이 좋습니다.  이 두 가지 방법 중 어떠한 방법으로 응용 프로그램을 실행 여부에 관계없이 모든 경우에 응용 프로그램의 다음 버전 또는 이전 버전과의 호환성에 영향을 줄 수 있는 릴리스 간의 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 변경 내용을 파악해야 합니다.  
  
## 다음 버전 및 이전 버전과의 호환성  
 다음 버전과의 호환성은 응용 프로그램이 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 이전 버전에서 컴파일될 수 있지만 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 다음 버전에서도 올바르게 실행되는 것을 뜻합니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1용으로 작성된 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 코드는 이후 버전과 호환됩니다.  
  
 이전 버전과의 호환성은 응용 프로그램이 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 새 버전용으로 컴파일되지만 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 이전 버전에서도 기능 손실 없이 실행되는 것을 뜻합니다.  물론 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 새 버전에 도입된 기능에는 해당되지 않습니다.  
  
## .NET Framework Data Provider for ODBC  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC\(<xref:System.Data.Odbc>\)는 버전 1.1부터 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 일부로 포함됩니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0 개발자는 [데이터 액세스 및 저장소 개발자 센터](http://go.microsoft.com/fwlink/?linkid=4173)\(영문\)에서 웹 다운로드로 ODBC 데이터 공급자를 사용할 수 있습니다.  다운로드한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for ODBC에 대한 네임스페이스는 **Microsoft.Data.Odbc**입니다.  
  
 ODBC 데이터 공급자를 사용하여 데이터 소스에 연결하는 응용 프로그램을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0용으로 개발하고 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1 이상 버전에서 해당 응용 프로그램을 실행하려고 할 경우, ODBC 데이터 공급자에 대한 네임스페이스를 **System.Data.Odbc**로 업데이트해야 합니다.  그런 다음 응용 프로그램을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 새 버전용으로 다시 컴파일해야 합니다.  
  
 ODBC 데이터 공급자를 사용하여 데이터 소스에 연결하는 응용 프로그램을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 2.0 이상용으로 개발하고 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0에서 해당 응용 프로그램을 실행하려고 할 경우, ODBC 데이터 공급자를 다운로드하여 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0 시스템에 설치해야 합니다.  그런 다음 ODBC 데이터 공급자에 대한 네임스페이스를 **Microsoft.Data.Odbc**로 변경하고 응용 프로그램을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0용으로 다시 컴파일해야 합니다.  
  
## .NET Framework Data Provider for Oracle  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle\(<xref:System.Data.OracleClient>\)은 버전 1.1부터 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 일부로 포함됩니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0 개발자는 [데이터 액세스 및 저장소 개발자 센터](http://go.microsoft.com/fwlink/?linkid=4173)\(영문\)에서 웹 다운로드로 데이터 공급자를 사용할 수 있습니다.  
  
 데이터 공급자를 사용하여 데이터 소스에 연결하는 응용 프로그램을 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 2.0 이상용으로 개발하고 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0에서 해당 응용 프로그램을 실행하려고 할 경우, 데이터 공급자를 다운로드하여 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0 시스템에 설치해야 합니다.  
  
## 코드 액세스 보안  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자\(<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>\)는 FullTrust 권한으로 실행해야 합니다.  FullTrust 권한이 없는 영역의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0에서 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자를 사용하려고 하면 <xref:System.Security.SecurityException>이 발생합니다.  
  
 그러나 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 2.0부터는 부분적으로 신뢰할 수 있는 영역에서 모든 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자를 사용할 수 있습니다.  또한 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 데이터 공급자에는 새로운 보안 기능이 추가되었습니다.  이 기능으로 특정 보안 영역에서 사용할 수 있는 연결 문자열을 제한할 수 있습니다.  뿐만 아니라 특정 보안 영역에 대해 빈 암호 사용을 비활성화할 수도 있습니다.  자세한 내용은 [코드 액세스 보안 및 ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)을 참조하세요.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 각 설치 환경에는 별도의 Security.config 파일이 있기 때문에 보안 설정과 관련한 호환성 문제가 없습니다.  그러나 응용 프로그램이 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1 이상에 포함된 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]의 추가 보안 기능을 사용하는 경우에는 응용 프로그램을 버전 1.0 시스템에 배포할 수 없습니다.  
  
## SqlCommand 실행  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1부터는 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>가 데이터 소스에서 명령을 실행하는 방식이 변경되었습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0에서 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>는 모든 명령을 **sp\_executesql** 저장 프로시저의 컨텍스트에서 실행합니다.  따라서 연결 상태에 영향을 주는 SET NOCOUNT ON과 같은 명령은 현재 명령의 실행에만 적용됩니다.  연결 상태는 연결이 열려 있는 동안 실행되는 모든 후속 명령에 대해 수정되지 않습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1 이상에서 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>는 명령에 매개 변수가 있을 경우 **sp\_executesql** 저장 프로시저의 컨텍스트에서 해당 명령만 실행하여 성능상의 이점을 제공합니다.  따라서 연결 상태에 영향을 주는 명령이 매개 변수가 없는 명령에 포함된 경우 연결이 열려 있는 동안 실행되는 모든 후속 명령의 연결 상태가 수정됩니다.  
  
 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> 호출에서 다음 배치 명령을 실행할 수 있습니다.  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.1 이상에서는 연결이 열려 있는 동안 실행되는 모든 후속 명령에 대해 NOCOUNT가 ON으로 유지됩니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 버전 1.0에서는 현재 명령을 실행할 때만 NOCOUNT가 ON이 됩니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 두 버전 각각에 대한 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>의 동작에 의존하는 경우 이 변경 내용은 응용 프로그램의 다음 버전 및 이전 버전과의 호환성에 모두 영향을 줄 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]의 이전 버전 및 다음 버전 모두에서 실행되는 응용 프로그램의 경우에는 실행 버전에 관계없이 동일하게 동작하도록 코드를 작성해야 합니다.  명령을 통해 모든 후속 명령에 대한 연결 상태가 수정되도록 하려면 <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>를 사용하여 명령을 실행하는 것이 좋습니다.  명령을 통해 모든 후속 명령에 대한 연결이 수정되지 않도록 하려면 명령에 연결 상태를 다시 설정하는 명령을 포함하는 것이 좋습니다.  예를 들면 다음과 같습니다.  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## 참고 항목  
 [ADO.NET 개요](../../../../docs/framework/data/adonet/ado-net-overview.md)   
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)