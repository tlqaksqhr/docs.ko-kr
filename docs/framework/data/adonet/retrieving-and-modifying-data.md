---
title: "ADO.NET에서 데이터 검색 및 수정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 722e7f87-3691-46c6-87e8-7d159722d675
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ff937e619d449fbfbedb234749292b6acc4bdf50
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="retrieving-and-modifying-data-in-adonet"></a>ADO.NET에서 데이터 검색 및 수정
데이터베이스 응용 프로그램의 기본 기능은 데이터 소스에 연결하여 포함된 데이터를 검색하는 것입니다. ADO.NET의.NET Framework 데이터 공급자 다리 역할을 응용 프로그램과 데이터 원본을 사용 하 여 데이터 검색 뿐 아니라 명령 실행 수는 **DataReader** 또는 **DataAdapter** . 모든 데이터베이스 응용 프로그램의 한 가지 핵심 기능은 데이터베이스에 저장된 데이터를 업데이트하는 것입니다. Ado.net에서 데이터 업데이트를 사용 하는 **DataAdapter** 및 <xref:System.Data.DataSet>, 및 **명령** 개체; 수 트랜잭션도 사용 해야 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [데이터 소스에 연결](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 데이터 소스에 대한 연결을 설정하고 연결 이벤트로 작업하는 방법을 설명합니다.  
  
 [연결 문자열](../../../../docs/framework/data/adonet/connection-strings.md)  
 연결 문자열 키워드, 보안 정보와 이에 대한 저장 및 검색을 비롯하여 다양한 연결 문자열 사용 방법을 설명하는 항목을 제공합니다.  
  
 [연결 풀링](../../../../docs/framework/data/adonet/connection-pooling.md)  
 .NET Framework 데이터 공급자의 연결 풀링에 대해 설명합니다.  
  
 [명령 및 매개 변수](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 명령 및 명령 작성기를 만드는 방법, 매개 변수를 구성하는 방법 및 명령을 실행하여 데이터를 검색하고 수정하는 방법에 대한 항목을 제공합니다.  
  
 [DataAdapter 및 DataReader](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 DataReaders, DataAdapters, 매개 변수, DataAdapter 이벤트 처리 및 배치 작업 수행 방법을 설명하는 항목을 제공합니다.  
  
 [트랜잭션 및 동시성](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 로컬 트랜잭션, 분산 트랜잭션 및 낙관적 동시성 관련 작업의 수행 방법을 설명하는 항목을 제공합니다.  
  
 [ID 또는 일련 번호 값 검색](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md)  
 에 대해 생성 된 값을 매핑할의 예제를 제공는 **identity** 열에는 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 테이블 또는 **일련 번호** 테이블에 삽입된 된 행의 열에는 Microsoft Access 테이블의 필드입니다. `DataTable`에서의 ID 값 병합에 대해 설명합니다.  
  
 [이진 데이터 검색](../../../../docs/framework/data/adonet/retrieving-binary-data.md)  
 이진 데이터 나 대형 데이터 구조를 사용 하 여 검색 하는 방법을 설명 `CommandBehavior`합니다.`SequentialAccess` 기본 동작을 수정 하는 `DataReader`합니다.  
  
 [저장 프로시저로 데이터 수정](../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 저장 프로시저 입력 매개 변수와 출력 매개 변수를 사용하여 데이터베이스에 행을 삽입하여 새 ID 값을 반환하는 방법을 설명합니다.  
  
 [데이터베이스 스키마 정보 검색](../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)  
 데이터 소스에서 사용 가능한 데이터베이스나 카탈로그, 데이터베이스의 테이블 및 뷰를 비롯하여 테이블에 대한 제약 조건 및 기타 스키마 정보를 가져오는 방법을 설명합니다.  
  
 [DbProviderFactory](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 공급자 팩터리 모델에 대해 설명하고 `System.Data.Common` 네임스페이스의 기본 클래스를 사용하는 방법을 보여 줍니다.  
  
 [ADO.NET의 데이터 추적](../../../../docs/framework/data/adonet/data-tracing.md)  
 ADO.NET에서 기본 제공 데이터 추적 기능을 제공하는 방법을 설명합니다.  
  
 [성능 카운터](../../../../docs/framework/data/adonet/performance-counters.md)  
 `SqlClient` 및 `OracleClient`에서 사용할 수 있는 성능 카운터에 대해 설명합니다.  
  
 [비동기 프로그래밍](../../../../docs/framework/data/adonet/asynchronous-programming.md)  
 비동기 프로그래밍에 대한 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 지원에 대해 설명합니다.  
  
 [SqlClient 스트리밍 지원](../../../../docs/framework/data/adonet/sqlclient-streaming-support.md)  
 메모리에 완전하게 로드하지 않고 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]에서 데이터를 스트리밍하는 응용 프로그램을 쓰는 방법에 대해 논의합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET에서 데이터 형식 매핑](../../../../docs/framework/data/adonet/data-type-mappings-in-ado-net.md)  
 [DataSet, DataTable 및 DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 응용 프로그램 보안](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server 및 ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
