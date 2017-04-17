---
title: "연결 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 연결 형식
*연결 형식*\(연결이라고도 함\)은 EDM\(엔터티 데이터 모델\)에서 관계를 설명하는 기본 구성 요소입니다.  개념적 모델에서 연결은 두 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md)\(예: `Customer` 및 `Order`\) 간의 관계를 나타냅니다.  응용 프로그램에서 연결 인스턴스는 특정 연결\(예: `Customer` 인스턴스와 `Order` 인스턴스 간의 연결\)을 나타냅니다.  연결 인스턴스는 [연결 집합](../../../../docs/framework/data/adonet/association-set.md)에 논리적으로 그룹화됩니다.  
  
 연결 정의에는 다음 정보가 들어 있습니다.  
  
-   고유한 이름  \(필수\)  
  
-   관계의 각 엔터티 형식을 나타내는 [연결 End](../../../../docs/framework/data/adonet/association-end.md) 두 개  \(필수\)  
  
    > [!NOTE]
    >  연결은 셋 이상 엔터티 형식 간의 관계를 나타낼 수 없습니다.  그러나 연결은 각 연결 End에 같은 엔터티 형식을 지정하여 자체 관계를 정의할 수 있습니다.  
  
-   [참조 무결성 제약 조건](../../../../docs/framework/data/adonet/referential-integrity-constraint.md) 이 매개 변수는 선택 사항입니다.  
  
 각 연결 End에는 연결의 한 End에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는 [연결 End 복합성](../../../../docs/framework/data/adonet/association-end-multiplicity.md)을 지정해야 합니다.  연결 End의 복합성 값은 한 개\(1\), 0개 또는 한 개\(0..1\) 또는 다수\(\*\)일 수 있습니다.  연결의 한 End에 있는 엔터티 형식 인스턴스는 엔터티 형식에서 노출된 경우 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 또는 외래 키를 통해 액세스할 수 있습니다.  자세한 내용은 [엔터티 데이터 모델: 외래 키](../../../../docs/framework/data/adonet/foreign-key-property.md)를 참조하세요.  
  
## 예제  
 다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.  `PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다.  `Publisher` 끝의 복합성은 한 개\(1\)이고 `Book` 끝의 복합성은 다수\(\*\)이므로 한 명의 발행자가 많은 책을 출판하고 책 하나는 한 명의 발행자에 의해 출판됨을 나타냅니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라는 DSL\(Domain\-Specific Language\)을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)