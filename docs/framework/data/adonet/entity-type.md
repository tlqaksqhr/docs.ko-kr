---
title: "엔터티 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 엔터티 형식
*엔터티 형식*은 EDM\(엔터티 데이터 모델\)을 사용하여 데이터 구조를 설명하기 위한 기본 구성 요소입니다.  개념적 모델에서 엔터티 형식은 고객이나 주문과 같은 최상위 개념의 구조를 나타냅니다.  엔터티 형식은 엔터티 형식 인스턴스의 템플릿입니다.  각 템플릿에는 다음 정보가 들어 있습니다.  
  
-   고유한 이름  \(필수\)  
  
-   하나 이상의 속성으로 정의된 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) \(필수\)  
  
-   [속성](../../../../docs/framework/data/adonet/property.md) 형식으로 된 데이터  \(선택적 요소\)  
  
-   [연결](../../../../docs/framework/data/adonet/association-type.md)의 한 [End](../../../../docs/framework/data/adonet/association-end.md)에서 다른 End로의 탐색을 허용하는 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 이 매개 변수는 선택 사항입니다.  
  
 응용 프로그램에서 엔터티 형식의 인스턴스는 특정 고객 또는 주문과 같은 특정 개체를 나타냅니다.  [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md) 내에 각 엔터티 형식 인스턴스에 대한 고유한 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md)가 있어야 합니다.  
  
 두 엔터티 형식 인스턴스는 형식이 동일하고 해당 엔터티 키 값이 동일한 경우에만 동일한 것으로 간주됩니다.  
  
## 예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 엔터티 키를 구성하는 각 엔터티 형식의 속성은 "\(키\)"로 표시됩니다.  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라는 DSL\(Domain\-Specific Language\)을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [패싯](../../../../docs/framework/data/adonet/facet.md)