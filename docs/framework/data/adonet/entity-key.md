---
title: "엔터티 키 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 엔터티 키
*엔터티 키*는 ID를 확인하는 데 사용되는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md)의 [속성](../../../../docs/framework/data/adonet/property.md) 또는 속성 집합입니다.  엔터티 키를 구성하는 속성은 디자인 타임에 선택됩니다.  엔터티 키 속성의 값은 런타임에 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md) 내에서 엔터티 형식 인스턴스를 고유하게 식별해야 합니다.  엔터티 키를 구성하는 속성을 선택하여 엔터티 집합에서 인스턴스의 고유성을 보장해야 합니다.  
  
 다음은 속성 집합이 엔터티 키가 되기 위한 요구 사항입니다.  
  
-   엔터티 집합 내의 두 엔터티 키는 같지 않아야 합니다.  즉, 엔터티 집합 내의 두 엔터티에서 키를 구성하는 모든 속성 값은 달라야 합니다.  그러나 엔터티 키를 구성하는 일부 값은 같을 수 있습니다.  
  
-   엔터티 키는 null을 허용하지 않고 변경할 수 없는 [기본 형식 속성](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)으로 구성되어야 합니다.  
  
-   지정된 엔터티 형식의 엔터티 키를 구성하는 속성은 변경할 수 없습니다.  지정된 엔터티 형식에 사용 가능한 엔터티 키를 여러 개 허용할 수는 없습니다. 서로게이트 키는 지원되지 않습니다.  
  
-   엔터티가 상속 계층 구조에 포함되어 있는 경우 루트 엔터티는 엔터티 키를 구성하는 모든 속성을 포함해야 하며, 루트 엔터티 형식에 엔터티 키를 정의해야 합니다.  자세한 내용은 [엔터티 데이터 모델: 상속](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)을 참조하세요.  
  
## 예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  엔터티 키를 구성하는 각 엔터티 형식의 속성은 "\(키\)"로 표시됩니다.  `Author` 엔터티 형식에는 두 가지 속성 `Name` 및 `Address`로 구성된 엔터티 키가 있습니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라는 DSL\(Domain\-Specific Language\)을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.  엔터티 키는 엔터티 형식의 `ISBN` 속성을 참조하여 정의됩니다.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 ISBN\(International Standard Book Number\)은 책을 고유하게 식별하므로 엔터티 키에 대해 `ISBN` 속성을 사용하는 것이 좋습니다.  
  
 다음 CSDL에서는 위의 다이어그램에 표시된 `Author` 엔터티 형식을 정의합니다.  엔터티 키는 두 가지 속성 `Name` 및 `Address`로 구성됩니다.  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 이름이 같은 두 저자가 같은 주소지에서 거주할 가능성은 없으므로 엔터티 키에 대해 `Name` 및 `Address`를 사용하는 것이 좋습니다.  그러나 이러한 엔터티 키 선택이 엔터티 집합에서의 고유한 엔터티 키를 절대적으로 보장하지는 않습니다.  이 경우에는 저자를 고유하게 식별하는 데 사용할 수 있는 `AuthorId`와 같은 속성을 추가하는 것이 좋습니다.  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)