---
title: "Entity SQL 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0bb8120-e709-40a3-ac1e-5520dc47477d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 301a934cad59b14d1a65a1e98247490d578e6866
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="entity-sql-overview"></a>Entity SQL 개요
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]은 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에서 개념적 모델을 쿼리하는 데 사용할 수 있는 SQL 유사 언어입니다. 개념적 모델 엔터티 및 관계로, 데이터를 표시 하 고 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 이러한 엔터티 및 관계 SQL을 사용한 사용자에 게 친숙 되는 형식으로 쿼리할 수 있습니다.  
  
 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]는 저장소별 데이터 공급자와 함께 작업하여 일반 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]을 저장소별 쿼리로 변환합니다. EntityClient 공급자는 엔터티 모델에 대해 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 명령을 실행하고 스칼라 결과, 결과 집합, 개체 그래프를 포함한 다양한 데이터 형식을 반환하는 방법을 제공합니다. <xref:System.Data.EntityClient.EntityCommand> 개체를 생성할 때 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리 문자열을 해당 <xref:System.Data.EntityClient.EntityCommand.CommandText%2A?displayProperty=nameWithType> 속성에 할당하여 저장 프로시저 이름 또는 쿼리 텍스트를 지정할 수 있습니다. <xref:System.Data.EntityClient.EntityDataReader>는 EDM에 대한 <xref:System.Data.EntityClient.EntityCommand> 실행 결과를 노출합니다. <xref:System.Data.EntityClient.EntityDataReader>를 반환하는 명령을 실행하려면 <xref:System.Data.EntityClient.EntityCommand.ExecuteReader%2A>를 호출합니다.  
  
 EntityClient 공급자 외에도 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에서 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]을 사용하여 개념적 모델에 대해 쿼리를 실행하고 엔터티 형식의 인스턴스인 강력한 형식의 CLR 개체로 데이터를 반환할 수 있습니다. 자세한 내용은 참조 [개체 작업](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md)합니다.  
  
 이 단원에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에 대한 개념 정보를 제공합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [Entity SQL TRANSACT-SQL의 차이점](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)  
  
 [Entity SQL 빠른 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-quick-reference.md)  
  
 [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)  
  
 [형식 정의](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)  
  
 [형식 생성](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)  
  
 [쿼리 계획을 캐시](../../../../../../docs/framework/data/adonet/ef/language-reference/query-plan-caching-entity-sql.md)  
  
 [네임스페이스](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
  
 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
  
 [매개 변수](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
  
 [변수](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md)  
  
 [지원 되지 않는 식](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)  
  
 [리터럴](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md)  
  
 [Null 리터럴 및 형식 유추](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)  
  
 [입력된 문자 집합](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)  
  
 [쿼리 식](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
  
 [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)  
  
 [연산자 우선 순위](../../../../../../docs/framework/data/adonet/ef/language-reference/operator-precedence-entity-sql.md)  
  
 [페이징](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
  
 [비교 의미 체계](../../../../../../docs/framework/data/adonet/ef/language-reference/comparison-semantics-entity-sql.md)  
  
 [중첩된 Entity SQL 쿼리 작성](../../../../../../docs/framework/data/adonet/ef/language-reference/composing-nested-entity-sql-queries.md)  
  
 [Null 허용 구조적된 형식](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Entity SQL 언어](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [CSDL, SSDL 및 MSL 사양](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
