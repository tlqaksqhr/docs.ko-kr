---
title: SQL Server에서 데이터 암호화
ms.date: 03/30/2017
ms.assetid: 83b992f7-b351-4678-b4b9-f4ffd58134cc
ms.openlocfilehash: 9e2924dc9f2f2954f6690ad5009c4143d1b9a44f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="data-encryption-in-sql-server"></a>SQL Server에서 데이터 암호화
SQL Server에는 인증서, 비대칭 키 또는 대칭 키를 사용하여 데이터를 암호화하고 해독하는 기능이 있습니다. 또한 SQL Server 2005는 내부 인증서 저장소에서 이러한 모든 항목을 관리합니다. 이 저장소는 계층 구조에서 한 단계 상위에 있는 계층에서 인증서와 키를 보호하는 암호화 계층 구조를 사용합니다. SQL Server의 이 기능 영역을 비밀 저장소라고 합니다.  
  
 암호화 기능에서 지원하는 가장 빠른 암호화 모드는 대칭 키 암호화입니다. 이 모드는 대량 데이터 처리에 적합합니다. 대칭 키는 인증서, 암호 또는 다른 대칭 키를 사용하여 암호화할 수 있습니다.  
  
## <a name="keys-and-algorithms"></a>키 및 알고리즘  
 SQL Server는 DES, Triple DES, RC2, RC4, 128비트 RC4, DESX, 128비트 AES, 192비트 AES 및 256비트 AES를 비롯한 다양한 대칭 키 암호화 알고리즘을 지원합니다. 이러한 알고리즘은 Windows Crypto API를 사용하여 구현됩니다.  
  
 데이터베이스 연결 범위 내에서 SQL Server는 공개 대칭 키를 여러 개 유지할 수 있습니다. 저장소에서 공개 키를 검색하여 데이터 암호 해독에 사용할 수 있습니다. 데이터 암호를 해독할 때에는 사용할 대칭 키를 지정할 필요가 없습니다. 각각의 암호화된 값에는 해독에 사용되는 키의 키 식별자(키 GUID)가 포함되어 있습니다. 엔진은 암호화된 바이트 스트림과 일치하는 공개 대칭 키를 찾아 올바른 키를 암호 해독하고 열었는지 확인합니다. 그런 다음 이 키를 사용하여 암호 해독을 수행하고 데이터를 반환합니다. 올바른 키가 열려 있지 않으면 NULL이 반환됩니다.  
  
 데이터베이스에 암호화 된 데이터로 작업 하는 방법을 보여 주는 예제를 보려면 [하는 방법: 데이터 열 암호화](http://go.microsoft.com/fwlink/?LinkID=128559) SQL Server 온라인 설명서의 합니다.  
  
## <a name="external-resources"></a>외부 리소스  
 데이터 암호화에 대한 자세한 내용은 다음 리소스를 참조하세요.  
  
|||  
|-|-|  
|[SQL Server 암호화](http://msdn.microsoft.com/library/bb510663.aspx) SQL Server 온라인 설명서의|SQL Server의 암호화에 대해 간략하게 설명합니다. 이 항목에는 추가 항목과 방법에 대한 링크도 포함되어 있습니다.|  
|[암호화 계층](http://msdn.microsoft.com/library/ms189586.aspx) 및 [암호화 방법 도움말 항목](http://msdn.microsoft.com/library/aa337557.aspx) SQL Server 온라인 설명서의|SQL Server의 암호화에 대해 간략하게 설명합니다. 이 항목에는 추가 항목과 방법에 대한 링크도 포함되어 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 응용 프로그램 보안](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server의 응용 프로그램 보안 시나리오](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [SQL Server에서 인증](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [SQL Server의 서버 및 데이터베이스 역할](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [SQL Server에서 소유권 및 사용자 스키마 분리](../../../../../docs/framework/data/adonet/sql/ownership-and-user-schema-separation-in-sql-server.md)  
 [SQL Server에서 권한 부여 및 권한](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
