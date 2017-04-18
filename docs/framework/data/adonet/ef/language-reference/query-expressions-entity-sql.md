---
title: "쿼리 식(Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 쿼리 식(Entity SQL)
쿼리 식은 다양한 쿼리 연산자를 단일 구문에 결합합니다.  [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 [리터럴](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [매개 변수](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [변수](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), 연산자, [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md), 집합 연산자 등을 포함하여 다양한 종류의 식을 제공합니다.  자세한 내용은 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)을 참조하세요.  
  
## 절  
 쿼리 식은 개체 컬렉션에 연속적인 연산을 적용하는 일련의 절로 구성되어 있으며,  표준 SQL SELECT 문에 있는 것과 동일한 절\([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [WHERE](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) 및 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)\)을 기반으로 합니다.  
  
## 범위  
 FROM 절에 정의된 이름이 나타나는 순서대로 왼쪽에서 오른쪽 순으로 FROM 범위에 제공됩니다.  JOIN 목록에서 식은 목록에서 앞쪽에 정의된 이름을 참조할 수 있습니다.  FROM 절에서 식별된 요소의 공용 속성은 FROM 범위에 추가되지 않으며 항상 정규화된 별칭 이름을 통해 참조해야 합니다.  일반적으로 select 식의 모든 부분은 FROM 범위 내에 있는 것으로 간주됩니다.  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)