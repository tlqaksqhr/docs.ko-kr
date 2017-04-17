---
title: "연산자 우선 순위(Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: e92e4ca5-2889-4266-9625-47f0eb01a948
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 연산자 우선 순위(Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 연산자가 여러 개 있는 경우 연산자 우선 순위에 따라 연산 수행 순서가 결정됩니다.  실행 순서는 쿼리 결과에 상당한 영향을 미칠 수 있습니다.  
  
 다음 표에서는 연산자 우선 순위를 보여 줍니다.  높은 수준의 연산자는 낮은 수준의 연산자보다 먼저 계산됩니다.  
  
|수준|연산 유형|연산자|  
|--------|-----------|---------|  
|1|기본 연산자|`. , [] ()`|  
|2|단항|`! not`|  
|3|곱하기|`* / %`|  
|4|더하기|`+ -`|  
|5|정렬|`< > <= >=`|  
|6|같음|`= != <>`|  
|7|조건부 AND|`and &&`|  
|8|조건부 OR|`or &#124;&#124;`|  
  
 식에 연산자 우선 순위 수준이 동일한 두 연산자가 있으면 쿼리 내의 위치를 기준으로 왼쪽에서 오른쪽으로 계산됩니다.  예를 들어,  `x+y-z` 는  `(x+y)-z`로 계산됩니다.  
  
 괄호를 사용하여 쿼리에서 연산자에 정의된 우선 순위를 재정의할 수 있습니다.  괄호 안의 모든 연산자를 먼저 계산하여 단일 결과를 생성한 후, 이 결과를 괄호 밖의 연산자에 사용할 수 있습니다.  예를 들어, `x+y*z`는 `y`를 `z`로 곱한 후 `x`를 더하지만, `(x+y)*z`는 `x`를 `y`에 더한 후 이 결과를 `z`로 곱합니다.  
  
## 참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)