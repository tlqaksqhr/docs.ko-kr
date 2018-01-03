---
title: "함수(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a195656d02d3b7e26ad4f0d8715fc8bf5663750b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="function-entity-sql"></a>함수(Entity SQL)
Entity SQL 쿼리 명령의 범위에서 함수를 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a>인수  
 `function-name`  
 함수의 이름입니다.  
  
 `parameter-name`  
 함수에 있는 매개 변수의 이름입니다.  
  
 `function_expression`  
 함수인 유효한 Entity SQL 식입니다. 함수의 명령은 함수에 전달된 `parameter_name` 매개 변수에 대해 작동할 수 있습니다.  
  
 `data_type`  
 지원되는 형식의 이름입니다.  
  
 COLLECTION ( <type_definition`>` )  
 지원되는 형식, 행 또는 참조 컬렉션을 반환하는 식입니다.  
  
 REF **(**`data_type`**)**  
 엔터티 형식에 대한 참조를 반환하는 식입니다.  
  
 ROW **(**`row_expression`**)**  
 하나 이상의 값에서 구조적으로 형식화된 익명 레코드를 반환하는 식입니다. 자세한 내용은 [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)을 참조하십시오.  
  
## <a name="remarks"></a>설명  
 함수 시그니처가 다르면 이름이 같은 여러 함수를 인라인으로 선언할 수 있습니다. 자세한 내용은 [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)을 참조하세요.  
  
 인라인 함수는 Entity SQL 명령에서 정의된 이후에야 해당 명령에서 호출될 수 있습니다. 그러나 인라인 함수는 호출된 함수가 정의되기 이전 또는 이후에 다른 인라인 함수 내에서 호출될 수 있습니다. 다음 예제에서는 함수 B가 정의되기 전에 함수 A에서 함수 B를 호출합니다.  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 자세한 내용은 [방법: 사용자 정의 함수 호출](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)을 참조하세요.  
  
 함수는 모델 자체에서도 선언할 수 있습니다. 모델에서 선언된 함수는 명령에서 인라인으로 선언된 함수와 동일한 방식으로 실행됩니다. 자세한 내용은 참조 [사용자 정의 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md)합니다.  
  
## <a name="example"></a>예  
 다음 Entity SQL 명령에서는 정수 값을 사용하여 반환된 제품을 필터링하는 `Products` 함수를 정의합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a>예  
 다음 Entity SQL 명령에서는 문자열 컬렉션을 사용하여 반환된 연락처를 필터링하는 `StringReturnsCollection` 함수를 정의합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Entity SQL 언어](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
