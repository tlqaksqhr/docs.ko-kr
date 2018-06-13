---
title: 사용자 정의 함수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
ms.openlocfilehash: a3c9cda162e77517d480d9e48eb80fa62dd1c161
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32764452"
---
# <a name="user-defined-functions-entity-sql"></a>사용자 정의 함수(Entity SQL)
Entity SQL에서는 쿼리에서 사용자 정의 함수를 호출할 수 있습니다. 쿼리와 함께 이러한 함수를 인라인으로 정의할 수 있습니다 (참조 [하는 방법: 사용자 정의 함수를 호출](http://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) 개념적 모델의 일부로 (참조 [하는 방법: 사용자 지정 함수를 개념적 모델에 정의](http://msdn.microsoft.com/library/0dad7b8b-58f6-4271-b238-f34810d68e5f)). Entity SQL 명령으로 개념적 모델 함수를 정의 [DefiningExpression](http://msdn.microsoft.com/library/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) 의 요소는 [함수](http://msdn.microsoft.com/library/dc3beca7-55cf-4977-8db0-5064cdbab134) 개념적 모델의 요소입니다.  
  
 Entity SQL을 통해 쿼리 명령 자체에서 함수를 정의할 수 있습니다. [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) 연산자는 인라인 함수를 정의 합니다. 함수 시그니처가 고유하면 단일 명령에서 여러 함수를 정의할 수 있으며, 이러한 함수는 이름이 같을 수 있습니다. 자세한 내용은 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
