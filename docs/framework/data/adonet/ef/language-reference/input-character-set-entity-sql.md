---
title: "입력 문자 집합(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13d291d3-e6bc-4719-b953-758b61a590b6
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1a830d9df1f94bd21689cba9a9893cb9c344dfdb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="input-character-set-entity-sql"></a>입력 문자 집합(Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 UTF-16으로 인코딩된 UNICODE 문자를 사용합니다.  
  
 문자열 리터럴은 작은따옴표로 묶인 임의의 UTF-16 문자(예: N'文字列リテラル')를 포함할 수 있습니다. 문자열 리터럴을 비교할 때 원래 UTF-16 값이 사용됩니다. 예를 들어, N'ABC'는 일본어와 라틴어에서 다릅니다.  
  
 주석은 모든 UTF-16 문자일 수 있습니다.  
  
 이스케이프 식별자는 대괄호 문자로 묶인 UTF-16 문자일 수 있습니다(예: [エスケープされた識別子])를 포함할 수 있습니다. 이스케이프된 UTF-16 식별자를 비교할 때 대/소문자는 구분되지 않습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 나타나는 모양은 같지만 서로 다른 코드 페이지에서 가져온 문자 버전을 다른 문자로 처리합니다. 예를 들어, 해당 문자가 동일한 코드 페이지에서 제공된 경우 [ABC]는 [abc]와 같습니다. 그러나 동일한 두 식별자가 서로 다른 코드 페이지에서 제공된 경우 두 식별자는 같지 않습니다.  
  
 공백은 UTF-16 공백 문자입니다.  
  
 줄 바꿈은 표준화된 UTF-16 줄 바꿈 문자입니다. 예를 들어, '\n' 및 '\r\n'은 줄 바꿈 문자로 인식되지만 '\r'은 줄 바꿈 문자가 아닙니다.  
  
 키워드, 식 및 문장 부호는 라틴어로 표준화된 UTF-16 문자일 수 있습니다. 예를 들어, 일본어 코드 페이지에서 SELECT는 유효한 키워드입니다.  
  
 키워드, 식 및 문장 부호는 라틴 문자일 수만 있습니다. 일본어 코드 페이지에서 `SELECT`는 키워드가 아닙니다. +, -, *, /, =, (, ), ‘, [, ] 및 여기에서 언급되지 않은 기타 언어 구문은 라틴 문자만 가능합니다.  
  
 단일 식별자는 라틴 문자만 가능합니다. 이렇게 하면 원래 값만 비교되므로 비교하는 동안 모호성을 피할 수 있습니다. 예를 들어, ABC는 일본어와 라틴어에서 다를 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
