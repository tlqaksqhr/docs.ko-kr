---
title: Entity Framework 데이터 공급자 작성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: cb969589afd4474d9bdfa3a475d8325c1717ab13
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="writing-an-entity-framework-data-provider"></a>Entity Framework 데이터 공급자 작성
이 섹션에서는 작성 하는 방법을 설명는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] SQL Server 이외의 데이터 소스를 지 원하는 공급자를 합니다. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 지 원하는 SQL Server 공급자가 포함 되어 있습니다.  
  
## <a name="introducing-the-entity-framework-provider-model"></a>Entity Framework 공급자 모델 소개  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]는 데이터베이스와 독립적이므로 다양한 데이터 소스 집합에 연결하기 위해 ADO.NET 공급자 모델을 사용하여 공급자를 작성할 수 있습니다.  
  
 Entity Framework 데이터 공급자(ADO.NET 데이터 공급자 모델을 사용하여 작성됨)는 다음과 같은 기능을 수행합니다.  
  
-   EDM(엔터티 데이터 모델) 기본 형식을 공급자 형식에 매핑합니다.  
  
-   공급자별 함수를 노출합니다.  
  
-   [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] 쿼리를 지원하기 위해 지정된 DbQueryCommandTree에 대한 공급자별 명령을 생성합니다.  
  
-   [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]를 통한 업데이트를 지원하기 위해 지정된 DbModificationCommandTree에 대한 공급자별 업데이트 명령을 생성합니다.  
  
-   데이터베이스 기반의 모델 생성을 지원하기 위해 저장소 스키마 정의에 대한 매핑 파일을 노출합니다.  
  
-   개념적 모델을 통해 메타데이터(예: 테이블 및 뷰)를 노출합니다.  
  
 ![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")  
  
## <a name="sample"></a>샘플  
 참조는 [Entity Framework 샘플 공급자](http://go.microsoft.com/fwlink/?LinkId=180616) 의 샘플는 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] SQL Server 이외의 데이터 소스를 지 원하는 공급자입니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [SQL 생성](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [수정 SQL 생성](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [공급자 매니페스트 지정](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a>참고 항목  
 [데이터 공급자 작업](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
