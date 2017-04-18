---
title: "DEREF(Entity SQL) | Microsoft Docs"
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
ms.assetid: 4c78e833-b260-453d-9bf4-eb39857dd0fa
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# DEREF(Entity SQL)
참조 값을 역참조하고 이 역참조의 결과를 생성합니다.  
  
## 구문  
  
```  
  
SELECT DEREF ( o.expression) from Table as o;  
```  
  
## 인수  
 `expression`  
 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.  
  
## 반환 값  
 참조되는 엔터티의 값입니다.  
  
## 설명  
 DEREF 연산자는 참조 값을 역참조하고 이 역참조의 결과를 생성합니다. 예를 들어, `r` 이 ref\<T\> 형식의 참조인 경우 `Deref``(r)`  `r`에서 참조하는 엔터티를 제시하는  `T`  형식의 식입니다. 참조 값이 null이거나 현수 참조\(참조 대상이 존재하지 않음\)인 경우 DEREF 연산자의 결과는 null입니다.  
  
## 예제  
 다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 DEREF 연산자를 사용하여 참조 값을 역참조하고 이 역참조의 결과를 생성합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: PrimitiveType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 ExecutePrimitiveTypeQuery 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#DEREF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#deref)]  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [REF](../../../../../../docs/framework/data/adonet/ef/language-reference/ref-entity-sql.md)   
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)   
 [KEY](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)   
 [null 허용 구조적 형식](../../../../../../docs/framework/data/adonet/ef/language-reference/nullable-structured-types-entity-sql.md)