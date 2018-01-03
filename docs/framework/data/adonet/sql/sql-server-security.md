---
title: "SQL Server 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
caps.latest.revision: "8"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4b8eafeedd03097488b1493b5654db360eab94fb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-security"></a>SQL Server 보안
[!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]에는 보안 데이터베이스 응용 프로그램을 만들 수 있도록 지원하는 많은 기능이 있습니다.  
  
 데이터 절도나 손상 같이 일반적으로 발생하는 보안 문제는 사용 중인 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 버전에 관계없이 항상 고려해야 할 사항입니다. 데이터 무결성도 보안 문제로 간주해야 합니다. 데이터를 보호하지 않으면 특수한 데이터 조작이 허용되어 실수나 악의적으로 데이터가 잘못된 값으로 수정되거나 완전히 삭제될 수 있으므로 데이터가 쓸모없게 될 수 있습니다. 또한 기밀 정보의 올바른 저장과 같이 반드시 지켜야 할 법적 요구 사항도 많습니다. 특정 관할권에서는 해당 법률에 따라 몇 가지 개인 데이터를 저장하는 것이 완전히 금지될 수도 있습니다.  
  
 Windows가 버전마다 다른 것처럼 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]도 버전마다 보안 기능이 다르며 최신 버전이 이전 버전보다 향상된 보안 기능을 가지고 있습니다. 하지만 보안 기능만으로는 데이터베이스 응용 프로그램의 보안을 보장할 수 없다는 점을 숙지해야 합니다. 데이터베이스 응용 프로그램은 각각 고유한 요구 사항, 실행 환경, 배포 모델, 실제 위치, 사용자 집단을 가집니다. 로컬에서만 실행되는 일부 응용 프로그램에는 최소한의 보안 기능만 있어도 되지만 대부분의 로컬 응용 프로그램이나 인터넷을 통해 배포되는 응용 프로그램에는 엄격한 보안 수단과 지속적인 모니터링 및 평가가 필요합니다.  
  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 데이터베이스 응용 프로그램의 보안 요구 사항은 디자인 타임부터 고려해야 하며 뒤늦게 생각해서는 안 됩니다. 개발 주기의 초기 단계에서 위협 요소를 평가하면 취약점이 발견되는 모든 부분의 손상 위험을 방지할 수 있습니다.  
  
 응용 프로그램의 초기 디자인이 뛰어나다고 해도 시스템이 발전함에 따라 새로운 위협 요소가 등장할 수 있습니다. 데이터베이스를 보호하는 여러 방어선을 만들면 보안 위반이 발생함으로써 입을 수 있는 손상을 최소화할 수 있습니다. 이중 가장 먼저 구축해야 할 방어선은 필요한 권한 이상의 권한이 부여되지 않게 하여 공격에 노출되는 영역을 줄이는 것입니다.  
  
 이 단원의 항목에서는 개발자와 관련이 있는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]의 보안 기능에 대해 간략히 설명하며, 이러한 항목에 대해 자세히 다루고 있는 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서와 기타 리소스의 관련 항목으로 연결되는 링크를 제공합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [SQL Server 보안 개요](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)]의 아키텍처와 보안 기능에 대해 설명합니다.  
  
 [SQL Server의 응용 프로그램 보안 시나리오](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 ADO.NET 및 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 응용 프로그램에 대한 다양한 응용 프로그램 보안 시나리오를 설명하는 항목을 제공합니다.  
  
 [SQL Server Express 보안](../../../../../docs/framework/data/adonet/sql/sql-server-express-security.md)  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] Express의 보안 고려 사항에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [보안 및 보호 (데이터베이스 엔진)](http://msdn2.microsoft.com/library/bb510589\(SQL.100\).aspx.)  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서의 보안 항목입니다.  
  
 [SQL Server에 대 한 보안 고려 사항](http://go.microsoft.com/fwlink/?LinkId=98587)  
 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 온라인 설명서의 보안 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 응용 프로그램 보안](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [SQL Server 및 ADO.NET](../../../../../docs/framework/data/adonet/sql/index.md)  
 [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](http://go.microsoft.com/fwlink/?LinkId=217917)
