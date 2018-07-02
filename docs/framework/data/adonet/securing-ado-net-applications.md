---
title: ADO.NET 응용 프로그램 보안
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: efe25082b4e4de9170179ebeff6a1dca8f67446c
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728604"
---
# <a name="securing-adonet-applications"></a>ADO.NET 응용 프로그램 보안
보안 ADO.NET 응용 프로그램을 작성하려면 사용자 입력의 유효성을 확인하지 않는 것과 같은 일반적인 코딩 문제를 피하는 것 외에도 여러 부분을 고려해야 합니다. 데이터에 액세스하는 응용 프로그램에는 공격자가 중요한 데이터를 검색, 조작 또는 파괴하는 데 악용할 수 있는 여러 잠재적인 오류 지점이 있습니다. 따라서 응용 프로그램 디자인 단계의 위협 모델링 과정에서부터 최종 배포와 진행 중인 유지 관리에 이르기까지 보안의 모든 측면을 이해해야 합니다.  
  
 .NET Framework에서는 데이터베이스 응용 프로그램을 보호하고 관리할 수 있는 여러 유용한 클래스, 서비스 및 도구를 제공합니다. CLR(공용 언어 런타임)은 관리 코드의 권한을 더 제한하는 CAS(코드 액세스 보안)를 사용하여 실행될 코드에 형식 안전 환경을 제공합니다. 다음 보안 데이터 액세스 코딩 연습에서는 잠재적인 공격자에 의해 발생할 수 있는 손상을 제한합니다.  
  
 보안 코드를 작성하면 데이터베이스와 같은 관리되지 않는 리소스 작업을 할 때 자초한 보안 허점을 막지 못합니다. SQL Server와 같은 대부분의 서버 데이터베이스는 제대로 구현되는 경우 보안을 강화하는 자체 보안 시스템을 가집니다. 그러나 제대로 구성되지 않은 경우 강력한 보안 시스템으로 구성된 데이터 소스라 할지라도 공격에 취약할 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [보안 개요](../../../../docs/framework/data/adonet/security-overview.md)  
 보안 ADO.NET 응용 프로그램 디자인에 대한 권장 사항을 제공합니다.  
  
 [보안 데이터 액세스](../../../../docs/framework/data/adonet/secure-data-access.md)  
 안전한 데이터 소스의 데이터로 작업하는 방법에 대해 설명합니다.  
  
 [안전한 클라이언트 응용 프로그램](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 클라이언트 응용 프로그램 보안을 위한 고려 사항에 대해 설명합니다.  
  
 [코드 액세스 보안 및 ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md)  
 CAS를 사용하여 ADO.NET 코드를 보호하는 방법 및 부분 신뢰를 사용하는 방법에 대해 설명합니다.  
  
 [개인 정보 및 데이터 보안](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 ADO.NET 응용 프로그램의 암호화 옵션에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [SQL Server 보안](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 개발자 관점에서 SQL Server 보안 기능에 대해 설명합니다.  
  
 [보안 고려 사항](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 Entity Framework 응용 프로그램의 보안에 대해 설명합니다.  
  
 [보안](../../../../docs/standard/security/index.md)  
 .NET에서 보안의 여러 가지 측면에 대해 설명하는 항목의 링크가 들어 있습니다.  
  
 [보안 도구](http://msdn.microsoft.com/library/2a3eb98a-2de6-4fba-b41c-01a74d354c11)  
 보안 정책을 보호하고 관리하는 .NET Framework 도구입니다.  
  
 [보안 응용 프로그램을 만들기 위한 리소스](http://msdn.microsoft.com/library/0ebf5f69-76f2-498a-a2df-83cf3443e132)  
 보안 응용 프로그램 만들기에 대한 항목의 링크를 제공합니다.  
  
 [보안 관련 참조 목록](/visualstudio/ide/security-bibliography)  
 온라인 및 인쇄 작업에서 사용 가능한 외부 리소스의 링크를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET](../../../../docs/framework/data/adonet/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
