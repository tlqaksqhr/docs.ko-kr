---
title: Entity Framework용 SqlClient에서 알려진 문제
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
caps.latest.revision: 2
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 8d5363ede9735ea805284638f795af67f2415ad0
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a>Entity Framework용 SqlClient에서 알려진 문제
이 단원에서는 .NET Framework Data Provider for SQL Server(SqlClient)와 관련된 알려진 문제에 대해 설명합니다.  
  
## <a name="trailing-spaces-in-string-functions"></a>문자열 함수의 후행 공백  
 SQL Server에는 문자열 값의 후행 공백을 무시 합니다. 따라서 문자열에 후행 공백을 전달 하면 예기치 않은 결과가 발생 하며 오류가 발생할 수 있습니다.  
  
 문자열에서 후행 공백을 포함 해야 할 경우 고려해 야 마지막에는 공백 문자를 추가 하 여 SQL Server 문자열을 트리밍 하지 않습니다. 후행 공백이 필요하지 않은 경우 쿼리 파이프라인을 통해 전달하기 전에 트리밍해야 합니다.  
  
## <a name="right-function"></a>RIGHT 함수  
 `null`이 아닌 값을 첫 번째 인수, 0을 두 번째 인수로 `RIGHT(nvarchar(max)`, 0`)` 또는 `RIGHT(varchar(max)`, 0`)`에 전달하면 `NULL` 문자열 대신 `empty` 값이 반환됩니다.  
  
## <a name="cross-and-outer-apply-operators"></a>CROSS 및 OUTER APPLY 연산자  
 CROSS 및 OUTER APPLY 연산자는 [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)]에서 도입되었습니다. 경우에 따라 쿼리 파이프라인에는 CROSS APPLY 및/또는 OUTER APPLY 연산자를 포함 하는 TRANSACT-SQL 문을 생성할 수 있습니다. 때문에 SQL Server의 버전을 비롯 한 일부 백엔드 공급자 보다 이전 [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)]를 이러한 연산자를 지원 하지 않으므로 해당 백엔드 공급자에서 쿼리를 실행할 수 없습니다.  
  
 다음은 출력 쿼리에 CROSS APPLY 및/또는 OUTER APPLY 연산자가 포함될 수 있는 일반적인 시나리오입니다.  
  
-   페이징이 있는 상호 관련된 하위 쿼리  
  
-   상호 관련된 하위 쿼리 또는 탐색으로 생성된 컬렉션에 대한 `AnyElement`  
  
-   요소 선택기를 허용하는 그룹화 메서드를 사용하는 LINQ 쿼리  
  
-   CROSS APPLY 또는 OUTER APPLY가 명시적으로 지정된 쿼리  
  
-   REF 구문보다 DEREF 구문을 우선 적용하는 쿼리  
  
## <a name="skip-operator"></a>SKIP 연산자  
 [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]을 사용하는 경우 키가 아닌 열에 ORDER BY와 함께 SKIP을 사용하면 잘못된 결과가 반환될 수 있습니다. 키가 아닌 열에 중복 데이터가 있는 경우, 지정된 개수 이상의 행을 건너뛸 수 있습니다. 이런 현상은 SKIP이 [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]에 맞게 변환되는 방식 때문에 발생합니다. 예를 들어 다음 쿼리에서 `E.NonKeyColumn`에 중복 값이 있으면 5개가 넘는 행을 건너뛸 수 있습니다.  
  
```  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a>올바른 SQL Server 버전을 대상으로 지정  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 대상은 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 에 지정 된 SQL Server 버전에 따라 쿼리는 `ProviderManifestToken` 저장소 모델 (.ssdl) 파일에 있는 Schema 요소의 특성입니다. 이 버전은 연결된 실제 SQL Server의 버전과 다를 수 있습니다. 예를 들어 SQL Server 2005를 사용하지만 `ProviderManifestToken` 특성이 2008로 설정된 경우 생성된 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 쿼리가 서버에서 실행되지 않을 수 있습니다. 예를 들어 SQL Server 2008에 도입 된 새 날짜 시간 형식을 사용 하는 쿼리는 이전 버전의 SQL Server에서 실행 되지 않습니다. SQL Server 2005를 사용하지만 `ProviderManifestToken` 특성이 2000으로 설정된 경우 생성된 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] 쿼리가 덜 최적화되거나, 쿼리가 지원되지 않는다는 예외가 표시될 수 있습니다. 자세한 내용은이 항목의 앞부분에 나오는 CROSS 및 OUTER APPLY 연산자 단원을 참조.  
  
 특정 데이터베이스 동작은 데이터베이스로 설정된 호환성 수준에 따라 달라집니다. `ProviderManifestToken` 특성이 2005로 설정되어 있고 SQL Server 버전은 2005지만 데이터베이스의 호환성 수준이 "80"(SQL Server 2000)으로 설정된 경우 생성된 [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]에서 SQL Server 2005를 대상으로 지정하지만 호환성 수준 설정으로 인해 예상대로 실행되지 않을 수 있습니다. 예를 들어, ORDER BY 목록의 열 이름이 선택기의 열 이름과 일치하는 경우 정렬 정보가 손실될 수 있습니다.  
  
## <a name="nested-queries-in-projection"></a>프로젝션의 중첩 쿼리  
 프로젝션 절의 중첩 쿼리는 서버의 Cartesian 제품 쿼리로 변환될 수 있습니다. SLQ Server를 비롯 한 일부 백엔드 서버에서이 수로 인해 TempDB 테이블이 매우 커질 수 있습니다. 서버 성능이 저하될 수 있습니다.  
  
 다음은 프로젝션 절의 중첩 쿼리 예제입니다.  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a>서버에서 생성된 GUID ID 값  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]에서는 서버에서 생성된 GUID 형식 ID 값을 지원하지만 공급자에서 행이 삽입된 이후 서버에서 생성된 ID 값을 반환하는 기능을 지원해야 합니다. SQL Server 2005 이상에서는 반환할 수 있습니다 서버 생성 GUID 형식을 통해 SQL Server 데이터베이스는 [OUTPUT 절](http://go.microsoft.com/fwlink/?LinkId=169400) 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Entity Framework용 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)  
 [LINQ to Entities에서 알려진 문제 및 고려 사항](../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)
