---
title: Oracle 및 ADO.NET
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
caps.latest.revision: 4
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 40b81df158dbad0247df76124201decae41e3267
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="oracle-and-adonet"></a>Oracle 및 ADO.NET
> [!NOTE]
>  <xref:System.Data.OracleClient>의 형식은 사용되지 않습니다. 이 형식은 현재 버전의 .NET Framework에서 계속 지원되지만 향후 릴리스에서 제거될 예정입니다. 타사 Oracle 공급자를 사용하는 것이 좋습니다.  
  
 이 단원에서는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle과 관련된 기능 및 동작에 대해 설명합니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle에서는 Oracle Client 소프트웨어에서 제공하는 OCI(Oracle Call Interface)를 사용하여 Oracle 데이터베이스에 액세스할 수 있습니다. 데이터 공급자의 기능은 유사 하지만 되도록 설계는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SQL Server, OLE DB 및 ODBC 데이터 공급자입니다.  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle을 사용하려면 다음과 같이 응용 프로그램에서 <xref:System.Data.OracleClient> 네임스페이스를 참조해야 합니다.  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 또한 코드를 컴파일할 때 DLL에 대한 참조를 포함해야 합니다. 예를 들어, C# 프로그램을 컴파일하는 경우 명령줄에 다음을 포함해야 합니다.  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>섹션 내용  
 [시스템 요구 사항](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Data Provider for Oracle을 사용하는 데 필요한 요구 사항 및 사용 과정에서 발생하는 몇 가지 알려진 문제점에 대해 설명합니다.  
  
 [Oracle BFILE](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 Oracle BFILE 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleBFile> 클래스에 대해 설명합니다.  
  
 [Oracle LOB](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 Oracle LOB 데이터 형식 작업에 사용되는 <xref:System.Data.OracleClient.OracleLob> 클래스에 대해 설명합니다.  
  
 [Oracle REF CURSOR](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 Oracle REF CURSOR 데이터 형식 지원에 대해 설명합니다.  
  
 [OracleType](../../../../docs/framework/data/adonet/oracletypes.md)  
 <xref:System.Data.OracleClient.OracleNumber> 및 <xref:System.Data.OracleClient.OracleString>을 비롯하여 Oracle 데이터 형식 작업에 사용할 수 있는 구조에 대해 설명합니다.  
  
 [Oracle 시퀀스](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 서버에서 생성한 Oracle 시퀀스 키 값을 검색하는 지원 기능에 대해 설명합니다.  
  
 [Oracle 데이터 형식 매핑](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Oracle 데이터 형식과 <xref:System.Data.OracleClient.OracleDataReader>에 대한 해당 데이터 형식의 매핑이 나열되어 있습니다.  
  
 [Oracle 분산 트랜잭션](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 <xref:System.Data.OracleClient.OracleConnection> 개체에서 트랜잭션이 활성화되어 있다고 판단할 경우 기존 분산 트랜잭션에 자동으로 인리스트먼트하는 방법을 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ADO.NET 응용 프로그램 보안](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]을 사용할 때 보안 코드를 작성하는 방법을 설명합니다.  
  
 [DataSet, DataTable 및 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 `DataSets`, 형식화된 `DataSets`, `DataTables` 및 `DataViews`를 만들고 사용하는 방법에 대해 설명합니다.  
  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 ADO.NET에서 데이터로 작업하는 방법을 설명합니다.  
  
 [SQL Server 및 ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 SQL Server 관련 기능을 사용하는 방법에 대해 설명합니다.  
  
 [DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]에서 공급자 독립적인 코드를 쓸 수 있게 하는 일반 클래스에 대해 설명합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
