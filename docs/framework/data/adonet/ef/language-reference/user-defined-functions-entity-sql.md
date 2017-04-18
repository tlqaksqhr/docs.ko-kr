---
title: "사용자 정의 함수(Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 사용자 정의 함수(Entity SQL)
Entity SQL에서는 쿼리에서 사용자 정의 함수를 호출할 수 있습니다.  이러한 함수를 쿼리에서 인라인으로 정의하거나\([How to: Call a User\-Defined Function](http://msdn.microsoft.com/ko-kr/ad131b86-8b4e-4747-8605-d4fc64fb9d02) 참조\) 개념적 모델의 일부로 정의할 수 있습니다\([How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/ko-kr/0dad7b8b-58f6-4271-b238-f34810d68e5f) 참조\).  개념적 모델 함수는 개념적 모델에 있는 [Function](http://msdn.microsoft.com/ko-kr/dc3beca7-55cf-4977-8db0-5064cdbab134) 요소의 [DefiningExpression](http://msdn.microsoft.com/ko-kr/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) 요소에서 Entity SQL 명령으로 정의됩니다.  
  
 Entity SQL을 통해 쿼리 명령 자체에서 함수를 정의할 수 있습니다.  [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) 연산자는 인라인 함수를 정의합니다.  함수 시그니처가 고유하면 단일 명령에서 여러 함수를 정의할 수 있으며, 이러한 함수는 이름이 같을 수 있습니다.  자세한 내용은 [함수 오버로드 확인](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md)을 참조하세요.  
  
## 참고 항목  
 [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)