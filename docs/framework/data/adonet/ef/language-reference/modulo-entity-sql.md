---
title: "% (모듈로)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 243ddc4f-3c4e-41e1-a3ef-4ed39e36248b
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a04b2972c80aff654331aeb319390b6f817374bc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="modulo-entity-sql"></a>% (모듈로)(Entity SQL)
한 식을 다른 식으로 나눈 나머지를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
dividend % divisor  
```  
  
## <a name="arguments"></a>인수  
 `dividend`  
 나눌 숫자 식입니다. `dividend` 는 숫자 데이터 형식의 유효한 식입니다.  
  
 `divisor`  
 피제수를 나눌 숫자 식입니다. `divisor` 는 숫자 데이터 형식의 유효한 식입니다.  
  
## <a name="result-types"></a>결과 형식  
 Edm.Int32  
  
## <a name="example"></a>예  
 다음 Entity SQL 쿼리에서는 % 산술 연산자를 사용하여 한 식을 다른 식으로 나눈 나머지를 반환합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#MODULO](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#modulo)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
