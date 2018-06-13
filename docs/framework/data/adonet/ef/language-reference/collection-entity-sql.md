---
title: COLLECTION(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
ms.openlocfilehash: 2b13d373e6c54221249b17de4fa91347cbc0f9e6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761635"
---
# <a name="collection-entity-sql"></a>COLLECTION(Entity SQL)
COLLECTION 키워드는 인라인 함수의 정의에만 사용됩니다. 컬렉션 함수는 값 컬렉션에 대해 작업을 수행하고 스칼라 출력을 생성하는 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a>인수  
 `type_definition`  
 지원되는 형식, 행 또는 참조 컬렉션을 반환하는 식입니다.  
  
## <a name="remarks"></a>설명  
 COLLECTION 키워드에 대한 자세한 내용은 [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md)항목을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 COLLECTION 키워드를 사용하여 10진수 컬렉션을 인라인 쿼리 함수의 인수로 선언하는 방법을 보여 줍니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
