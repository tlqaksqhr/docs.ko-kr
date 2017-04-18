---
title: "+ (문자열 연결)(Entity SQL) | Microsoft Docs"
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
ms.assetid: 580130fa-6c7c-4f76-a47d-d22c27ccadf6
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# + (문자열 연결)(Entity SQL)
두 문자열을 연결합니다.  
  
## 구문  
  
```  
  
expression  
+  
expression  
  
```  
  
## 인수  
 `expression`  
 EDM.String 데이터 형식의 유효한 식입니다. 두 식의 데이터 형식이 같거나 한 식이 다른 식의 데이터 형식으로 암시적으로 변환될 수 있어야 합니다.  
  
## 결과 형식  
 두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다. 암시적 형식 승격에 대한 자세한 내용은 [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md) 항목을 참조하세요.  
  
## 예제  
 다음 Entity SQL 쿼리에서는 \+ 연산자를 사용하여 두 문자열을 연결합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: PrimitiveType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#CONCAT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#concat)]  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [개념적 모델 형식\(CSDL\)](http://msdn.microsoft.com/ko-kr/987b995f-e429-4569-9559-b4146744def4)