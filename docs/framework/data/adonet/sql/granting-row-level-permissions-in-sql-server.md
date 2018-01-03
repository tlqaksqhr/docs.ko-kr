---
title: "SQL Server에서 행 수준 권한 부여"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a55aaa12-34ab-41cd-9dec-fd255b29258c
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a42c8d24a2817fb0a4118927722e7ac1887517a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="granting-row-level-permissions-in-sql-server"></a>SQL Server에서 행 수준 권한 부여
일부 시나리오에서는 권한 부여, 취소 또는 거부를 통해 제공되는 것보다 세부적인 수준으로 데이터에 대한 액세스를 제어해야 합니다. 예를 들어 병원용 데이터베이스 응용 프로그램에서는 개별 의사가 담당 환자에 관련된 정보에만 액세스하도록 제한해야 할 수 있습니다. 재무, 법률, 정부 및 군사용 응용 프로그램을 비롯한 다양한 환경에도 이러한 요구 사항이 적용될 수 있습니다. 이러한 시나리오를 해결할 수 있도록 SQL Server 2016에서는 보안 정책에서 행 수준 액세스 논리를 간소화하고 중앙 집중화하는 [행 수준 보안](https://msdn.microsoft.com/library/dn765131.aspx) 기능을 제공합니다. 초기 버전 SQL Server에서는 뷰를 사용하여 행 수준 필터링을 시행하는 방식으로 비슷한 기능을 적용할 수 있습니다.  
  
## <a name="implementing-row-level-filtering"></a>행 수준 필터링 구현  
 행 수준 필터링은 위의 병원 예제처럼 정보를 단일 테이블에 저장하는 응용 프로그램에 사용됩니다. 행 수준 필터링을 구현하기 위해 각 행에는 사용자 이름, 레이블 또는 식별자와 같은 식별 매개 변수를 정의하는 열이 있습니다. 사용자가 액세스할 수 있는 행을 필터링하는 보안 정책 또는 테이블의 뷰를 만듭니다. 그리고 사용자가 실행할 수 있는 쿼리 형식을 제어하는 매개 변수화된 저장 프로시저를 만듭니다.  
  
 다음 예제에서는 사용자 또는 로그인 이름을 기준으로 행 수준 필터링을 구성하는 방법을 설명합니다.  
  
-   테이블을 만들고, 이름을 저장할 열을 추가합니다.  
  
-   행 수준 필터링을 사용하도록 설정합니다.  
  
    -   SQL Server 2016 이상이 사용 하는 경우 또는 [Azure SQL 데이터베이스](https://docs.microsoft.com/azure/sql-database/), 현재 데이터베이스 사용자 (CURRENT_USER는 사용 중 하 나와 일치 하는 것 반환 되는 행을 제한 하는 테이블에 있는 조건자를 추가 하는 보안 정책을 만듭니다 기본 제공 함수 사용) 또는 현재 로그인 이름 (suser_sname () 기본 제공 함수 사용):  
  
        ```tsql  
        CREATE SCHEMA Security  
        GO  
  
        CREATE FUNCTION Security.userAccessPredicate(@UserName sysname)  
            RETURNS TABLE  
            WITH SCHEMABINDING  
        AS  
            RETURN SELECT 1 AS accessResult  
            WHERE @UserName = SUSER_SNAME()  
        GO  
  
        CREATE SECURITY POLICY Security.userAccessPolicy  
            ADD FILTER PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable,  
            ADD BLOCK PREDICATE Security.userAccessPredicate(UserName) ON dbo.MyTable  
        GO  
        ```  
  
    -   SQL Server 2016 이전 버전을 사용하고 있으면 뷰를 사용하여 비슷한 기능을 적용할 수 있습니다.  
  
        ```tsql  
        CREATE VIEW vw_MyTable  
        AS  
            RETURN SELECT * FROM MyTable  
            WHERE UserName = SUSER_SNAME()  
        GO  
        ```  
  
-   저장 프로시저를 만들어서 데이터를 선택, 삽입, 업데이트, 삭제합니다. 필터링이 보안 정책을 통해 시행되면 저장 프로시저는 기본 테이블에서 직접 이들 작업을 수행해야 합니다. 그렇지 않고 필터링이 뷰를 통해 시행되면 저장 프로시저는 대신 뷰에서 작업을 수행해야 합니다. 보안 정책 또는 뷰에서는 사용자 쿼리를 통해 반환 또는 수정되는 행을 자동으로 필터링하고, 저장 프로시저에서는 직접 쿼리 권한을 가진 사용자가 필터링된 데이터를 방해할 수 있는 쿼리를 실행하지 못하도록 더 강력한 보안 경계를 제공합니다.  
  
-   데이터를 삽입하는 저장 프로시저의 경우 보안 정책이나 뷰에 지정한 것과 동일한 함수를 사용하여 사용자 이름을 캡처하고 해당 값을 UserName 열에 삽입합니다.  
  
-   `public` 역할에 대해 테이블 및 뷰(적용 가능한 경우)에 대한 모든 권한을 거부합니다. 필터 조건자는 역할이 아니라 사용자 이름 또는 로그인 이름을 기반으로 하기 때문에 사용자는 다른 데이터베이스 역할에서 권한을 상속할 수 없습니다.  
  
-   데이터베이스 역할에 저장 프로시저에 대한 EXECUTE 권한을 부여합니다. 사용자는 제공된 저장 프로시저를 통해서만 데이터에 액세스할 수 있습니다.  
  
## <a name="external-resources"></a>외부 리소스  
 자세한 내용은 다음 리소스를 참조하세요.  
  
|||  
|-|-|  
|SQL Server TechCenter 사이트에서[SQL Server 2005를 사용하여 분류된 데이터베이스에서 행 및 셀 수준의 보안 성능을 구현](http://go.microsoft.com/fwlink/?LinkId=98227) 합니다.|행 및 셀 수준의 보안을 사용하여 기밀 데이터베이스의 보안 요구 사항을 충족하는 방법을 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [행 수준 보안](https://msdn.microsoft.com/library/dn765131.aspx)  
 [ADO.NET 응용 프로그램 보안](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server 보안 개요](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [SQL Server의 응용 프로그램 보안 시나리오](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [SQL Server에서 저장 프로시저를 사용하여 권한 관리](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [SQL Server에서 동적 보안 SQL 작성](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
