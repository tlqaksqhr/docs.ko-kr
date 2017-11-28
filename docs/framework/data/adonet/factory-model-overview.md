---
title: "팩터리 모델 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 54d8db28fec710aba2307d826e147eb9bab13ab9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="factory-model-overview"></a>팩터리 모델 개요
ADO.NET 2.0에서는 <xref:System.Data.Common> 네임스페이스에 새로운 기본 클래스가 추가되었습니다. 이러한 기본 클래스는 추상적이기 때문에 직접 인스턴스화할 수 없습니다. 여기에는 <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand> 및 <xref:System.Data.Common.DbDataAdapter>가 포함되며 세 클래스 모두 <xref:System.Data.SqlClient> 및 <xref:System.Data.OleDb>와 같은 .NET Framework 데이터 공급자에서 공유됩니다. 기본 클래스를 사용하면 새 인터페이스를 만들 필요 없이 .NET Framework 데이터 공급자에 기능을 간편하게 추가할 수 있습니다.  
  
 또한 ADO.NET 2.0에서는 추상 기본 클래스가 도입되어 개발자가 특정 데이터 공급자에 한정되지 않는 제네릭 데이터 액세스 코드를 작성할 수 있습니다.  
  
## <a name="the-factory-design-pattern"></a>팩터리 디자인 패턴  
 공급자에 독립적인 코드를 작성하기 위한 프로그래밍 모델은 단일 API를 사용하여 여러 공급자의 데이터베이스에 액세스하는 "팩터리" 디자인 패턴을 기본적으로 사용합니다. 이 패턴은 이름에서 알 수 있듯이 실제 팩터리와 마찬가지로 다른 개체를 만들기 위해서만 특수 개체를 사용해야 합니다. 팩터리 디자인 패턴의 보다 자세한 설명을 참조 하십시오. "[ASP.NET 2.0 및 ADO.NET 2.0에서 제네릭 데이터 액세스 코드를 작성](http://go.microsoft.com/fwlink/?LinkId=55915)" 및 "일반 코딩 된 the ADO.NET 2.0 기본 클래스 및 팩터리" [http:// msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) msdn 합니다.  
  
 ADO.NET 2.0부터 <xref:System.Data.Common.DbProviderFactories> 클래스는 `static` 인스턴스를 만드는 `Shared`(Visual Basic의 경우 <xref:System.Data.Common.DbProviderFactory>) 메서드를 제공합니다. 그러면 이 인스턴스는 런타임에 제공되는 공급자 정보와 연결 문자열을 기반으로 강력한 형식의 개체를 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Dbproviderfactory 가져오기](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [DbConnection, DbCommand 및 DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [DbDataAdapter로 데이터 수정](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
