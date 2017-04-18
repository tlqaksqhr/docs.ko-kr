---
title: "지원되지 않는 식(Entity SQL) | Microsoft Docs"
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
  - "ESQL"
ms.assetid: 5e79da7e-e78a-413c-8fb0-f3f9cd84f579
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 지원되지 않는 식(Entity SQL)
이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되지 않는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 식에 대해 설명합니다. 자세한 내용은 [Entity SQL과 Transact\-SQL 비교](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)를 참조하세요.  
  
## 정규화된 조건자  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서는 다음 폼을 생성할 수 있습니다.  
  
```  
sal > all (select salary from employees)  
sal > any (select salary from employees)  
```  
  
 이와 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 생성이 지원되지 않습니다.  대신 이와 동등한 식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 다음과 같이 쓸 수 있습니다.  
  
```  
not exists(select 0 from employees as e where sal > e.salary)  
exists(select 0 from employees as e where sal > e.salary)  
```  
  
## \* 연산자  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서는 모든 열이 프로젝션되어야 함을 나타내도록 SELECT 절에서 \* 연산자를 사용하도록 지원합니다.  이는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 지원되지 않습니다.  
  
## 참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)   
 [Entity SQL과 Transact\-SQL 비교](../../../../../../docs/framework/data/adonet/ef/language-reference/how-entity-sql-differs-from-transact-sql.md)