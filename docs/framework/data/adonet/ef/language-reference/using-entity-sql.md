---
title: USING(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c506484908d6b0ffe3a11e33b51d0bcc2d27c25c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
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
