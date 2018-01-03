---
title: "-- (주석)(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d9de735-2099-47f1-b7e7-60856f494924
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 483e1c69aea94375983acd840f84512de54bc746
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="---comment-entity-sql"></a>-- (주석)(Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에는 주석이 포함될 수 있습니다. 주석 줄은 대시 두 개(`--`)로 시작됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
-- text_of_comment  
```  
  
## <a name="arguments"></a>인수  
 `text_of_comment`  
 주석의 텍스트를 포함하는 문자열입니다.  
  
## <a name="example"></a>예  
 다음 Entity SQL 쿼리에서는 주석을 사용하는 방법을 보여 줍니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#COMMENT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#comment)]  
  
## <a name="see-also"></a>참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
