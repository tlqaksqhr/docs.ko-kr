---
title: 이어야 합니다. (멤버 액세스)(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4733e3b2-3efa-4b96-b591-ac31350e96ad
ms.openlocfilehash: fdcd026d245b3f6d6ecaccc0f828f3d77fd6ce1a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="-member-access-entity-sql"></a>이어야 합니다. (멤버 액세스)(Entity SQL)
점 (.) 연산자는는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 멤버 액세스 연산자입니다. 멤버 액세스 연산자를 사용하여 구조 개념적 모델 형식 인스턴스의 속성 또는 필드 값을 구합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression.identifier  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 구조 개념적 모델 형식의 인스턴스입니다.  
  
 `identifier`  
 개체 인스턴스에 속하는 속성 또는 필드입니다.  
  
## <a name="remarks"></a>설명  
 점 연산자(.)는 복합 형식 또는 엔터티 형식의 속성을 추출하는 것과 유사하게 레코드에서 필드를 추출하는 데 사용할 수 있습니다. 예를 들어 Name 형식의 n이 Person 형식의 멤버이고 p가 Person 형식의 인스턴스인 경우, p.n은 Name 형식의 값을 제공하는 유효한 멤버 액세스 식입니다.  
  
 `select p.Name.FirstName from LOB.Person as p`  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
