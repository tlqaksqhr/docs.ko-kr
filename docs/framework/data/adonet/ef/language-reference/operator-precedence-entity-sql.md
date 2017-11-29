---
title: "연산자 우선 순위(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 484eedffeaffb625cd43352dadedb8c99fbc65ed
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="operator-precedence-entity-sql"></a>연산자 우선 순위(Entity SQL)
경우는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 여러 명의 연산자, 연산자 우선 순위가 연산 수행 순서를 결정 합니다. 실행 순서는 쿼리 결과에 상당한 영향을 미칠 수 있습니다.  
  
 다음 표에서는 연산자 우선 순위를 보여 줍니다. 높은 수준의 연산자는 낮은 수준의 연산자보다 먼저 계산됩니다.  
  
|수준|연산 유형|연산자|  
|-----------|--------------------|--------------|  
|1|기본 연산자|`. , [] ()`|  
|2|단항|`! not`|  
|3|곱하기|`* / %`|  
|4|더하기|`+ -`|  
|5|정렬|`< > <= >=`|  
|6|같음|`= != <>`|  
|7|조건부 AND|`and &&`|  
|9|조건부 OR|`or &#124;&#124;`|  
  
 식에 연산자 우선 순위 수준이 동일한 두 연산자가 있으면 쿼리 내의 위치를 기준으로 왼쪽에서 오른쪽으로 계산됩니다. 예를 들어, `x+y-z`는 `(x+y)-z`로 계산됩니다.  
  
 괄호를 사용하여 쿼리에서 연산자에 정의된 우선 순위를 재정의할 수 있습니다. 괄호 안의 모든 연산자를 먼저 계산하여 단일 결과를 생성한 후, 이 결과를 괄호 밖의 연산자에 사용할 수 있습니다. 예를 들어 `x+y*z` 곱합니다 `y` 여 `z` 다음 추가 `x`, 하지만 `(x+y)*z` 추가 `x` 를 `y` 을 다음 기준으로 결과 곱합니다 `z`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
