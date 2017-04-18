---
title: "매개 변수(Entity SQL) | Microsoft Docs"
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
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 매개 변수(Entity SQL)
매개 변수는 일반적으로 호스트 언어에서 사용되는 바인딩 API를 통해 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 외부에서 정의되는 변수입니다.  각 매개 변수에는 이름과 형식이 있습니다.  매개 변수 이름은 쿼리 식에서 정의되며 at\(@\) 기호가 접두사로 사용되므로, 쿼리에서 정의되는 속성 이름이나 다른 이름과 쉽게 구분할 수 있습니다.  
  
 호스트 언어 바인딩 API는 매개 변수 바인딩을 위한 API를 제공합니다.  
  
## 예제  
  
```  
select c   
      from LOB.Customers as c   
      where c.Name = @name  
```  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)