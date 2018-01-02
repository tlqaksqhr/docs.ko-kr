---
title: "형식 생성(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41fa7bde-8d20-4a3f-a3d2-fb791e128010
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: a10ac4f8b89259c7d5ff46ad99ad6c8a925726d1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="constructing-types-entity-sql"></a>형식 생성(Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]세 가지 종류의 생성자를 제공: 행 생성자, 명명 된 형식 생성자 및 컬렉션 생성자입니다.  
  
## <a name="row-constructors"></a>행 생성자  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 행 생성자를 사용하여 값 하나 이상을 기반으로 구조적으로 형식화된 익명 레코드를 생성합니다. 행 생성자의 결과 형식은 필드 형식이 행 생성에 사용된 값의 형식과 동일한 행 형식입니다. 예를 들어 다음 식은 `Record(a int, b string, c int)` 형식의 값을 생성합니다.  
  
 `ROW(1 AS a, "abc" AS b, a + 34 AS c)`  
  
 행 생성자에서 식의 별칭을 제공하지 않으면 Entity Framework에서 별칭을 생성합니다. 자세한 내용은의 "별칭 지정 규칙" 섹션을 참조 하십시오. [식별자](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)합니다.  
  
 행 생성자에서 식에 별칭을 지정하는 데 다음 규칙이 적용됩니다.  
  
-   행 생성자의 식은 동일한 생성자 내의 다른 별칭을 참조할 수 없습니다.  
  
-   동일한 행 생성자 내의 서로 다른 두 식은 별칭이 같을 수 없습니다.  
  
 행 생성자에 대 한 자세한 내용은 참조 [행](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md)합니다.  
  
## <a name="collection-constructors"></a>컬렉션 생성자  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 컬렉션 생성자를 사용하여 값 목록에서 multiset 인스턴스를 만듭니다. 생성자의 모든 값은 상호 호환되는 `T` 형식이어야 하며, 생성자는 `Multiset<T>` 형식의 컬렉션을 생성합니다. 예를 들어, 다음 식은 정수 컬렉션을 만듭니다.  
  
 `Multiset(1, 2, 3)`  
  
 `{1, 2, 3}`  
  
 빈 multiset 생성자는 요소 형식을 확인할 수 없으므로 사용할 수 없습니다. 다음은 유효하지 않습니다.  
  
 `multiset() {}`  
  
 자세한 내용은 참조 [MULTISET](../../../../../../docs/framework/data/adonet/ef/language-reference/multiset-entity-sql.md)합니다.  
  
## <a name="named-type-constructors-namedtype-initializers"></a>명명된 형식 생성자(NamedType 이니셜라이저)  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 형식 생성자(이니셜라이저)는 명명된 복합 형식과 엔터티 형식 인스턴스를 만들 수 있습니다. 예를 들어, 다음 식은 `Person` 형식의 인스턴스를 만듭니다.  
  
 `Person("abc", 12)`  
  
 다음 식은 복합 형식의 인스턴스를 만듭니다.  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 다음 식은 중첩된 복합 형식의 인스턴스를 만듭니다.  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 다음 식은 중첩된 복합 형식을 가진 엔터티의 인스턴스를 만듭니다.  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 다음 예제에서는 복합 형식의 속성을 null로 초기화하는 방법을 보여 줍니다. `MyModel.ZipCode(‘98118’, null)`  
  
 생성자의 인수는 형식의 특성 선언과 동일한 순서인 것으로 가정됩니다.  
  
 자세한 내용은 참조 [명명 된 형식 생성자](../../../../../../docs/framework/data/adonet/ef/language-reference/named-type-constructor-entity-sql.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [형식 시스템](../../../../../../docs/framework/data/adonet/ef/language-reference/type-system-entity-sql.md)
