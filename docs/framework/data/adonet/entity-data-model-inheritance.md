---
title: '엔터티 데이터 모델: 상속'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: c5c1b385ea72e48fd70ed5ec0cf8d1c42c1284e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32765271"
---
# <a name="entity-data-model-inheritance"></a>엔터티 데이터 모델: 상속
(EDM (엔터티 데이터 모델)에 대 한 상속 지원 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md)합니다. EDM의 상속은 개체 지향 프로그래밍 언어의 클래스에 대한 상속과 유사합니다. 개체 지향 언어의 클래스와 함께 개념적 모델에서 정의한 엔터티 형식 처럼 (한 *파생 형식*) 다른 엔터티 형식에서 상속 되는 (의 *기본 형식*). 그러나 개체 지향 프로그래밍의 클래스와 달리 개념적 모델에서 파생 된 형식 항상 모든 상속 된 [속성](../../../../docs/framework/data/adonet/property.md) 및 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 기본 형식입니다. 파생 형식에서 상속된 속성을 재정의할 수는 없습니다.  
  
 개념적 모델에서는 파생 형식이 다른 파생 형식으로부터 상속받는 상속 계층 구조를 작성할 수 있습니다. 계층 (파생 형식이 아닌 계층의 한 유형)의 최상위에 있는 형식의 라고는 *루트 형식*합니다. 상속 계층 구조의 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 루트 형식에서 정의 되어야 합니다.  
  
 파생 형식이 둘 이상의 형식으로부터 상속받는 상속 계층 구조는 작성할 수 없습니다. 예를 들어, `Book` 엔터티 형식이 포함된 개념적 모델에서는 각각 `FictionBook`으로부터 상속되는 파생 형식 `NonFictionBook`과 `Book`을 정의할 수 있습니다. 그러나 `FictionBook` 및 `NonFictionBook` 형식에서 모두 상속되는 형식을 정의할 수는 없습니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 네 가지 엔터티 형식 `Book`, `FictionBook`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다. `FictionBook` 엔터티 형식은 `Book` 엔터티 형식에서 상속되는 파생 형식입니다. `FictionBook` 형식은 `ISBN (Key)`, `Title` 및 `Revision` 속성을 상속하고 `Genre`라는 추가 속성을 정의합니다.  
  
 ![상속](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `FictionBook` 형식에서 상속되는 엔터티 형식 `Book`을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
