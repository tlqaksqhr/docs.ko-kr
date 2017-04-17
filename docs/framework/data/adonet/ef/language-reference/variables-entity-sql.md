---
title: "변수(Entity SQL) | Microsoft Docs"
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
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 변수(Entity SQL)
## 변수  
 변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다.  변수 참조는 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)에 정의된 대로 유효한 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식별자여야 합니다.  
  
 다음 예제에서는 식에서 변수 사용을 보여 줍니다.  FROM 절의 `c`는 변수 정의입니다.  SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.  
  
```  
select c   
from LOB.customers as c  
```  
  
## 참고 항목  
 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)   
 [매개 변수](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)   
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)