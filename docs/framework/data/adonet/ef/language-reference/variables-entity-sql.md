---
title: "변수(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: fff24c4572fab483c701a93167c0f229d5111d61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="variables-entity-sql"></a>변수(Entity SQL)
## <a name="variable"></a>변수  
 변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다. 변수 참조는 유효 해야 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식별자에 정의 된 대로 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)합니다.  
  
 다음 예제에서는 식에서 변수 사용을 보여 줍니다. FROM 절의 `c`는 변수 정의입니다. SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.  
  
```  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>참고 항목  
 [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)  
 [매개 변수](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md)  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
