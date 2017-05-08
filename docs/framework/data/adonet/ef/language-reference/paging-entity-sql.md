---
title: "페이징(Entity SQL) | Microsoft Docs"
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
ms.assetid: ba4f334d-03e5-4a7b-9d42-628f4639b9a2
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 페이징(Entity SQL)
[ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 절의 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) 및 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) 하위 절을 사용하여 물리적 페이징을 수행할 수 있습니다.  결정적인 방법으로 물리적 페이징을 수행하려면 SKIP과 LIMIT를 사용해야 합니다.  비결정적인 방법으로 결과의 행의 수만 제한하려면 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)을 사용해야 합니다.  TOP과 SKIP\/LIMIT는 함께 사용할 수 없습니다.  
  
## TOP 개요  
 SELECT 절에는 선택적인 TOP 하위 절과 선택적인 ALL\/DISTINCT 한정자를 차례로 사용할 수 있습니다.  TOP 하위 절은 쿼리 결과에 첫 번째 행 집합만 반환되도록 지정합니다.  자세한 내용은 [TOP](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)을 참조하세요.  
  
## SKIP 및 LIMIT 개요  
 SKIP과 LIMIT는 ORDER BY 절의 일부입니다.  SKIP 식 하위 절이 ORDER BY 절에 있으면 결과는 정렬 기준에 따라 정렬되고 SKIP 식 바로 뒤에 있는 행에서 시작하는 행이 결과 집합에 포함됩니다.  예를 들어, SKIP 5를 사용하면 처음 다섯 개의 행을 건너뛰고 여섯 번째 행부터 반환됩니다.  LIMIT 식 하위 절이 ORDER BY 절에 있으면 쿼리는 정렬 지정에 따라 정렬되고 결과 행의 수는 LIMIT 식으로 제한됩니다.  예를 들어, LIMIT 5는 결과 집합을 다섯 개의 인스턴스 또는 행으로 제한합니다.  SKIP과 LIMIT를 반드시 함께 사용해야 하는 것은 아니므로 ORDER BY 절에 SKIP과 LIMIT 중 하나만 사용할 수 있습니다.  자세한 내용은 다음 항목을 참조하세요.  
  
-   [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
  
-   [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
  
-   [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [How to: Page Through Query Results](http://msdn.microsoft.com/ko-kr/ffc0f920-e7de-42e0-9b12-ef356421d030)