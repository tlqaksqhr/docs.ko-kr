---
title: THEN(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 99fd941c963ff87203d7b315beb606d40001224d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="then-entity-sql"></a>THEN(Entity SQL)
WHEN 절이 `true`로 계산될 때의 결과입니다.  
  
## <a name="syntax"></a>구문  
  
```  
WHEN when_expression THEN then_expression  
```  
  
## <a name="arguments"></a>인수  
 `when_expression`  
 모든 유효한 부울 식입니다.  
  
 `then_expression`  
 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.  
  
## <a name="remarks"></a>설명  
 `when_expression` 이 `true`값으로 계산되면 결과는 해당 `then-expression`입니다. 만족되는 WHEN 조건이 없으면 `else-expression` 이 계산됩니다. 하지만 `else-expression`이 없으면 결과는 null입니다.  
  
 예를 들어 참조 [대/소문자](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)합니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 CASE 식을 사용하여 일련의 `Boolean` 식을 계산합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>참고 항목  
 [대/소문자](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
