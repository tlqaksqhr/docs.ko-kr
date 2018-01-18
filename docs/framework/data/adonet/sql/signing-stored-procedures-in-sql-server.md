---
title: "SQL Server에서 저장 프로시저에 서명"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: "6"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a3f1ed66ed7caf2272ca27097dc9a838bec7d0ae
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a>SQL Server에서 저장 프로시저에 서명
인증서나 비대칭 키를 사용하여 저장 프로시저에 서명할 수 있습니다. 이 기능은 권한을 소유권 체인을 통해 상속할 수 없거나 동적 SQL과 같이 소유권 체인이 끊어진 시나리오를 위해 디자인되었습니다. 인증서에 매핑된 사용자를 만들고 저장 프로시저에서 액세스해야 하는 개체에 대한 인증서 사용자 권한을 부여할 수 있습니다.  
  
 저장 프로시저가 실행되면 SQL Server에서 인증서 사용자의 권한을 호출자의 권한과 결합합니다. EXECUTE AS 절과는 달리 프로시저의 실행 컨텍스트는 변경하지 않습니다. 로그인과 사용자 이름을 반환하는 기본 제공 함수는 인증서 사용자 이름이 아니라 호출자의 이름을 반환합니다.  
  
 디지털 설명은 서명자의 개인 키로 암호화된 데이터 다이제스트입니다. 개인 키를 사용하면 디지털 서명이 소유자별로 고유하게 유지됩니다. 저장 프로시저, 함수 또는 트리거에 서명할 수 있습니다.  
  
> [!NOTE]
>  master 데이터베이스에서 인증서를 만들어 서버 수준 권한을 부여할 수 있습니다.  
  
## <a name="creating-certificates"></a>인증서 만들기  
 저장 프로시저에 인증서로 서명할 때는 저장 프로시저 코드의 암호화된 해시로 구성된 데이터 다이제스트가 개인 키를 사용하여 만들어집니다. 런타임에 데이터 다이제스트는 공개 키로 암호 해독되어 저장 프로시저의 해시 값과 비교됩니다. 저장 프로시저를 수정하면 해시 값이 무효화되어 디지털 서명이 더 이상 일치하지 않습니다. 이를 통해 개인 키에 대한 액세스 권한이 없는 사용자는 저장 프로시저 코드를 변경할 수 없습니다. 따라서 프로시저를 수정할 때마다 다시 서명해야 합니다.  
  
 모듈에 서명할 때는 다음 네 단계를 수행합니다.  
  
1.  Transact-SQL `CREATE CERTIFICATE [certificateName]` 문을 사용하여 인증서를 만듭니다. 이 문에는 시작 및 종료 날짜와 암호를 설정하기 위한 몇 가지 옵션이 있습니다. 기본 만료일은 1년입니다.  
  
2.  Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 문을 사용하여 해당 인증서와 연결된 데이터베이스 사용자를 만듭니다. 이 사용자는 데이터베이스에만 존재하며 로그인과는 관련되지 않습니다.  
  
3.  데이터베이스 개체에 대해 필요한 권한을 인증서 사용자에게 부여합니다.  
  
> [!NOTE]
>  인증서는 DENY 문을 사용하여 호출된 권한을 가진 사용자에게 권한을 부여할 수 없습니다. DENY는 항상 GRANT보다 높은 우선 순위를 갖기 때문에 호출자가 인증서 사용자에게 부여된 권한을 상속 받지 않도록 방지합니다.  
  
1.  Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 문을 사용하여 프로시저에 인증서로 서명합니다.  
  
## <a name="external-resources"></a>외부 리소스  
 자세한 내용은 다음 리소스를 참조하세요.  
  
|리소스|설명|  
|--------------|-----------------|  
|[모듈 서명](http://go.microsoft.com/fwlink/?LinkId=98590) SQL Server 온라인 설명서의|모듈 서명을 설명하고 샘플 시나리오 및 관련 Transact-SQL 항목 링크를 제공합니다.|  
|[인증서로 저장된 프로시저에 서명](http://msdn.microsoft.com/library/bb283630.aspx) SQL Server 온라인 설명서의|인증서로 저장 프로시저에 서명하는 방법에 대한 자습서를 제공합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 응용 프로그램 보안](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server 보안 개요](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [SQL Server의 응용 프로그램 보안 시나리오](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [SQL Server에서 저장 프로시저를 사용하여 권한 관리](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [SQL Server에서 동적 보안 SQL 작성](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [SQL Server에서 가장으로 권한 사용자 지정](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [저장 프로시저로 데이터 수정](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
