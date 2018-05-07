---
title: SQL Server 보안 개요
ms.date: 03/30/2017
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
ms.openlocfilehash: 84b6724417d03a30c131700e197744839d3a020d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="overview-of-sql-server-security"></a>SQL Server 보안 개요
보안 위협에 대처하는 가장 좋은 방법은 여러 보안 계층으로 구성된 심층적인 방어 전략을 구현하는 것입니다. SQL Server는 데이터베이스 관리자와 개발자가 안전한 데이터베이스 응용 프로그램과 위협 대처 방안을 만들 수 있도록 디자인된 보안 아키텍처를 제공합니다. SQL Server의 각 버전은 새로운 기능이 추가되어 이전 버전의 SQL Server에 비해 향상되었지만 사용자 환경에 맞게 직접 보안을 구성하고 설정해야 합니다. 보안 요구 사항은 응용 프로그램마다 다릅니다. 따라서 개발자는 알려진 위협에 대응하는 데 가장 적합한 기능의 조합이 무엇인지 파악하고 향후 발생할 수 있는 위협에 대비할 수 있어야 합니다.  
  
 SQL Server 인스턴스에는 서버를 비롯한 여러 엔터티의 계층 구조적 컬렉션이 포함됩니다. 각 서버에는 여러 개의 데이터베이스가 있고, 각 데이터베이스에는 보안 개체의 컬렉션이 들어 있습니다. 모든 SQL Server 보안 개체에 연결 된 *권한을* 에 부여할 수 있습니다는 *주*, 되는 개인 사용자, 그룹 또는 SQL Server에 액세스 권한을 부여한 프로세스입니다. SQL Server 보안 프레임 워크를 통해 보안 엔터티에 대 한 액세스를 관리 *인증* 및 *권한 부여*합니다.  
  
-   인증은 보안 주체가 서버에서 확인하는 자격 증명을 제출하여 액세스를 요청함으로써 SQL Server에 로그온하는 프로세스입니다. 인증을 통해 사용자 또는 프로세스의 ID가 인증됩니다.  
  
-   권한 부여는 특정 보안 주체가 액세스할 수 있는 보안 리소스 및 해당 리소스에 대해 허용되는 작업을 결정하는 프로세스입니다.  
  
 이 단원의 항목에서는 SQL Server 보안 기본 사항에 대해 설명하며 보다 자세한 설명을 볼 수 있는 SQL Server 온라인 설명서의 해당 항목에 대한 링크를 제공합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [SQL Server에서 인증](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 SQL Server의 로그인 및 인증에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.  
  
 [SQL Server의 서버 및 데이터베이스 역할](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 고정 서버 역할과 데이터베이스 역할, 사용자 지정 데이터베이스 역할 및 기본 제공 계정에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.  
  
 [SQL Server에서 소유권 및 사용자 스키마 분리](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 개체 소유권과 사용자 스키마 분리에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.  
  
 [SQL Server에서 권한 부여 및 권한](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 최소 권한 원칙을 사용하여 권한을 부여하는 방법에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.  
  
 [SQL Server에서 데이터 암호화](../../../../../docs/framework/data/adonet/sql/data-encryption-in-sql-server.md)  
 SQL Server의 데이터 암호화 옵션에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.  
  
 [SQL Server의 CLR 통합 보안](../../../../../docs/framework/data/adonet/sql/clr-integration-security-in-sql-server.md)  
 CLR 통합 보안 리소스에 대한 링크를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 응용 프로그램 보안](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server 보안](../../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 [SQL Server의 응용 프로그램 보안 시나리오](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
