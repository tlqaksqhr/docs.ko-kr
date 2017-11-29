---
title: DbProviderFactory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2a8e2640-3a49-42a1-a3a9-b43026907ae1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e8c6310b8ce164a60541dae030ce603bccd372e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="dbproviderfactories"></a>DbProviderFactory
<xref:System.Data.Common> 네임스페이스에서는 특정 데이터 소스를 사용하기 위해 <xref:System.Data.Common.DbProviderFactory> 인스턴스를 만드는 데 필요한 클래스를 제공합니다. <xref:System.Data.Common.DbProviderFactory> 인스턴스를 만든 다음 이 인스턴스에 데이터 공급자에 대한 정보를 전달하면 `DbProviderFactory`에서 제공된 정보에 따라 반환할 강력한 형식의 올바른 연결 개체를 결정할 수 있습니다.  
  
 .NET Framework 버전 4부터는 <xref:System.Data.Odbc>, <xref:System.Data.OleDb>, <xref:System.Data.SqlClient> 및 <xref:System.Data.OracleClient> 등의 데이터 공급자는 더 이상 제공되지 않지만 사용자 지정 공급자는 계속 표시됩니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [팩터리 모델 개요](../../../../docs/framework/data/adonet/factory-model-overview.md)  
 팩터리 디자인 패턴 및 프로그래밍 인터페이스를 간략히 소개합니다.  
  
 [Dbproviderfactory 가져오기](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 설치된 데이터 공급자를 나열하고 <xref:System.Data.Common.DbConnection>에서 `DbProviderFactory`을 만드는 방법을 보여 줍니다.  
  
 [DbConnection, DbCommand 및 DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 <xref:System.Data.Common.DbCommand> 및 <xref:System.Data.Common.DbDataReader>를 만들고 <xref:System.Data.Common.DbException>을 사용하여 데이터 오류를 처리하는 방법을 보여 줍니다.  
  
 [DbDataAdapter로 데이터 수정](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 <xref:System.Data.Common.DbCommandBuilder>를 <xref:System.Data.Common.DbDataAdapter>와 함께 사용하여 데이터를 검색 및 수정하는 방법을 보여 줍니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET에서 데이터 검색 및 수정](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
