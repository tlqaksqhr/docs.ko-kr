---
title: "SQL Server에서 저장 프로시저에 서명"
ms.custom: 
ms.date: 01/05/2018
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eeed752c-0084-48e5-9dca-381353007a0d
caps.latest.revision: 
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 15771cc214ee17bc2c98bab2423013483d1355f1
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="signing-stored-procedures-in-sql-server"></a>SQL Server에서 저장 프로시저에 서명
 디지털 설명은 서명자의 개인 키로 암호화된 데이터 다이제스트입니다. 개인 키를 사용하면 디지털 서명이 소유자별로 고유하게 유지됩니다. 저장된 프로시저, 함수 (인라인 테이블 반환 함수)를 제외한, 트리거 및 어셈블리를 서명할 수 있습니다.  
  
 인증서나 비대칭 키를 사용하여 저장 프로시저에 서명할 수 있습니다. 이 기능은 권한을 소유권 체인을 통해 상속할 수 없거나 동적 SQL과 같이 소유권 체인이 끊어진 시나리오를 위해 디자인되었습니다. 그런 다음 인증서를 저장된 프로시저에 액세스 해야 하는 개체에 대 한 사용자 권한을 부여 인증서에 매핑된 사용자를 만들 수 있습니다.  

 동일한 인증서에 매핑된 로그인을 만들 및 다음 해당 로그인에 필요한 서버 수준 사용 권한을 부여 하거나 수도 하나 이상의 고정된 서버 역할에 로그인을 추가 합니다. 사용 하지 않도록 설정 하도록 설계 되어는 `TRUSTWORTHY` 데이터베이스 더 높은 수준의 사용 권한이 필요한 시나리오에 대 한 설정입니다.  
  
 저장된 프로시저를 실행 하면 SQL Server와 호출자의 로그인 및/또는 인증서 사용자의 사용 권한을 결합 합니다. 와 달리는 `EXECUTE AS` 절, 프로시저의 실행 컨텍스트를 변경 되지 않습니다. 로그인과 사용자 이름을 반환하는 기본 제공 함수는 인증서 사용자 이름이 아니라 호출자의 이름을 반환합니다.  
  
## <a name="creating-certificates"></a>인증서 만들기  
 인증서 나 비대칭 키를 execute와 함께 저장된 프로시저 코드의 암호화 된 해시로 구성 된 데이터 다이제스트가로 저장된 프로시저를 등록 하면-개인 키를 사용 하 여 만든이 사용자로 합니다. 런타임에 데이터 다이제스트는 공개 키로 암호 해독되어 저장 프로시저의 해시 값과 비교됩니다. Execute 변경-대로 디지털 서명을 더 이상 일치 하도록 사용자 해시 값을 무효화 합니다. 저장된 프로시저 수정 삭제 서명을 완전히 방지 하는 코드를 변경 하면 저장된 프로시저에서 개인 키에 대 한 액세스 권한이 없는 사람이 합니다. 두 경우 모두 다시 서명 해야 프로시저 코드 또는 execute를 변경할 때마다-사용자로 합니다.  
  
 모듈에 서명할에 관련 된 두 단계가 있습니다.  
  
1.  Transact-SQL `CREATE CERTIFICATE [certificateName]` 문을 사용하여 인증서를 만듭니다. 이 문에는 시작 및 종료 날짜와 암호를 설정하기 위한 몇 가지 옵션이 있습니다. 기본 만료 날짜는 1 년입니다.  
  
1.  Transact-SQL `ADD SIGNATURE TO [procedureName] BY CERTIFICATE [certificateName]` 문을 사용하여 프로시저에 인증서로 서명합니다.  

모듈에 서명 된 후 하나 이상의 보안 주체 인증서에 연결 해야 하는 추가 권한을 보유 하기 위해 만들 수 있어야 합니다.  

모듈이 데이터베이스 수준 사용 권한을 추가 해야 하는 경우:  
  
1.  Transact-SQL `CREATE USER [userName] FROM CERTIFICATE [certificateName]` 문을 사용하여 해당 인증서와 연결된 데이터베이스 사용자를 만듭니다. 이 사용자는 데이터베이스에 있으며 로그인도 동일한 인증서에서 생성 된 경우가 아니면 로그인과 연결 되어 있지 않습니다.  
  
1.  인증서 사용자에 게 필요한 데이터베이스 수준 사용 권한을 부여 합니다.  
  
모듈 추가 서버 수준 권한이 있어야 하는 경우:  
  
1.  인증서를 복사는 `master` 데이터베이스입니다.  
 
1.  TRANSACT-SQL을 사용 하 여 해당 인증서와 연결 된 로그인 만들기 `CREATE LOGIN [userName] FROM CERTIFICATE [certificateName]` 문.  
  
1.  인증서 로그인 필요한 서버 수준 사용 권한을 부여 합니다.  
  
> [!NOTE]  
>  인증서는 DENY 문을 사용하여 호출된 권한을 가진 사용자에게 권한을 부여할 수 없습니다. DENY는 항상 GRANT보다 높은 우선 순위를 갖기 때문에 호출자가 인증서 사용자에게 부여된 권한을 상속 받지 않도록 방지합니다.  
  
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
