---
title: 밀접하게 결합된 클라이언트-서버 응용 프로그램을 사용한 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
ms.openlocfilehash: f094bb319a4ca5241e60993770c9c49c3151635c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33359922"
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a>밀접하게 결합된 클라이언트-서버 응용 프로그램을 사용한 LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프레젠테이션 계층에 있는 밀접 하 게 결합 된 스마트 클라이언트와 중간 계층에서 사용할 수 있습니다. 읽기 전용 데이터 액세스를 사용하고 낙관적 동시성 검사 또는 타임스탬프를 사용하는 낙관적 동시성 검사가 필요하지 않은 시나리오에서는 로컬 시나리오에 비해 작업이 크게 복잡하지 않습니다. 그러나 데이터베이스에서 원래 값을 사용하여 낙관적 동시성 검사를 수행해야 할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 데이터 집합을 사용할 때와는 달리 데이터 라운드트립을 지원하지 않습니다. 하지만 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 중간 계층은 모든 종류의 플랫폼에 있는 클라이언트와 데이터를 교환할 수 있습니다.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] 클라이언트에 serialize 된 후 엔터티 상태를 추적 하는 인프라가 없는 제공 합니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 데이터와 프레젠테이션 계층 간의 상호 작용은 작고 비교적 원자적 인 서비스 지향 아키텍처를 사용 하도록 설정 하지만 원래 값의 라운드트립은 수행 하지 않습니다. 따라서 밀접하게 결합된 스마트 클라이언트와 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하려는 경우 데이터베이스에서 원래 값을 사용하여 낙관적 동시성 검사를 사용한다면 프레젠테이션 계층과 중간 계층 사이에 변경 내용을 통신하는 메커니즘을 직접 구현해야 합니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]이 중간 계층에서 제공하는 이점을 활용할 수 있도록 이와 같은 추가 작업을 수행할지 여부는 시스템 디자이너가 결정할 사항입니다. 그러나 데이터베이스에서 타임스탬프를 사용하는 경우에는 변경 내용 추적 논리를 사용자 지정할 필요가 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL을 사용한 N 계층 및 원격 응용 프로그램](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [웹 서비스를 사용하는 LINQ to SQL N 계층](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [n 계층 응용 프로그램에서 데이터 집합 작업](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)
