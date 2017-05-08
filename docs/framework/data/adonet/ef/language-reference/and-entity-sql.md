---
title: "&amp;&amp;(AND)(Entity SQL) | Microsoft Docs"
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
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# &amp;&amp;(AND)(Entity SQL)
두 식이 `true`이면 `true`를 반환하고, 그렇지 않으면 `false` 또는 `NULL`을 반환합니다.  
  
## 구문  
  
```  
  
          boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## 인수  
 `boolean_expression`  
 부울을 반환하는 모든 유효한 식입니다.  
  
## 설명  
 이중 앰퍼샌드\(&&\)는 AND 연산자와 같은 기능을 합니다.  
  
 다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|TRUE|FALSE|NULL|  
|`FALSE`|FALSE|FALSE|FALSE|  
|`NULL`|NULL|FALSE|NULL|  
  
## 예제  
 다음 Entity SQL 쿼리에서는 AND 연산자를 사용하는 방법을 보여 줍니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)