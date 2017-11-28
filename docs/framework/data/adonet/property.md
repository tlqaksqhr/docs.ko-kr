---
title: "속성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c052c53488fde0ea767a46f51ef349dd6a7d2766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="property"></a>속성
*속성* 의 기본적인 구성 요소는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 및 [복합 형식을](../../../../docs/framework/data/adonet/complex-type.md)합니다. 속성은 엔터티 형식 인스턴스 또는 복합 형식 인스턴스에 포함될 데이터의 모양과 특징을 정의합니다. 개념적 모델의 속성은 클래스에 정의된 속성과 유사합니다. 클래스의 속성이 클래스의 모양을 정의하고 개체에 대한 정보를 전달하는 것과 동일한 방식으로, 개념적 모델의 속성은 엔터티 형식의 모양을 정의하고 엔터티 형식 인스턴스에 대한 정보를 전달합니다.  
  
> [!NOTE]
>  이 항목에서 설명하는 속성은 탐색 속성과는 다릅니다. 자세한 내용은 참조 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md)합니다.  
  
 속성 정의에는 다음 정보가 들어 있습니다.  
  
-   속성 이름 (필수)  
  
-   속성 형식 (필수)  
  
-   집합이 [패싯](../../../../docs/framework/data/adonet/facet.md)합니다. 이 매개 변수는 선택 사항입니다.  
  
 속성에는 기본 데이터(예: 문자열, 정수 또는 부울 값) 또는 구조적 데이터(예: 복합 형식)가 포함될 수 있습니다. 기본 형식인 속성을 스칼라 속성이라고도 합니다. 자세한 내용은 참조 [엔터티 데이터 모델: 기본 데이터 형식](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)합니다.  
  
> [!NOTE]
>  복합 형식 자체에 복합 형식인 속성이 있을 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다. 각 속성의 형식 정보는 다이어그램에 표시되지 않지만 각 엔터티 형식에는 여러 속성이 있습니다. 속성을 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) (키)로 표시 됩니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의하고 XML 특성을 사용하여 각 속성의 형식과 이름을 나타냅니다. 선택적 패싯인 `Nullable`도 XML 특성을 사용하여 정의됩니다.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 다이어그램에 표시된 속성 중 하나는 복합 형식 속성일 수 있습니다. 예를 들어, `Address` 엔터티 형식의 `Publisher` 속성은 `StreetAddress`, `City`, `StateOrProvince`, `Country` 및 `PostalCode`와 같은 여러 스칼라 속성으로 구성된 복합 형식 속성일 수 있습니다. 이러한 복합 형식의 CSDL 표현은 다음과 같습니다.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
