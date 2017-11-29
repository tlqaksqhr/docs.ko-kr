---
title: REF(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: dfc91b60c68f55def8e7f81c2c5dd068c23f6e69
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ref-entity-sql"></a>REF(Entity SQL)
엔터티 인스턴스에 대한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
REF( expression )   
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 엔터티 형식의 인스턴스를 생성하는 모든 유효한 식입니다.  
  
## <a name="return-value"></a>반환 값  
 지정한 엔터티 인스턴스에 대한 참조입니다.  
  
## <a name="remarks"></a>설명  
 엔터티 참조는 엔터티 키와 엔터티 집합 이름으로 구성됩니다. 여러 엔터티 집합이 같은 엔터티 형식을 기반으로 할 수 있으므로 특정 엔터티 키가 여러 엔터티 집합에 나타날 수 있습니다. 하지만 엔터티 참조는 항상 고유합니다. 입력 식이 보관된 엔터티를 나타내는 경우 이 엔터티에 대한 참조가 반환됩니다. 입력 식이 보관된 엔터티가 아닌 경우 Null 참조가 반환됩니다.  
  
 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스하면 해당 참조가 자동으로 역참조됩니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리는 REF 연산자를 사용하여 입력 엔터티 인수에 대한 참조를 반환합니다. 속성 추출 연산자(.)를 사용하여 Product 엔터티의 속성에 액세스하고 있으므로 같은 쿼리에서 참조를 역참조합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#REF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref)]  
  
## <a name="see-also"></a>참고 항목  
 [DEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/deref-entity-sql.md)  
 [CREATEREF](../../../../../../docs/framework/data/adonet/ef/language-reference/createref-entity-sql.md)  
 [키](../../../../../../docs/framework/data/adonet/ef/language-reference/key-entity-sql.md)  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [형식 정의](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)
