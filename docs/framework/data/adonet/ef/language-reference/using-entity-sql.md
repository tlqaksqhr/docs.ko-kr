---
title: USING(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 89306c8b4c317ebaba0d964869c4fe9e1028631a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762340"
---
# <a name="using-entity-sql"></a>USING(Entity SQL)
쿼리 식에 사용되는 네임스페이스를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>인수  
 `alias`  
 네임스페이스를 정규화하는 데 사용할 짧은 별칭을 지정합니다.  
  
 `namespace`  
 유효한 네임스페이스입니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 USING 연산자를 사용하여 쿼리 식에 사용되는 네임스페이스를 지정합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
```  
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>참고 항목  
 [네임스페이스](../../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
