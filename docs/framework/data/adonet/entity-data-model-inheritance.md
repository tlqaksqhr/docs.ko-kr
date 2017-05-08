---
title: "엔터티 데이터 모델: 상속 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 엔터티 데이터 모델: 상속
EDM\(엔터티 데이터 모델\)에서는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md)에 대해 상속을 지원합니다.  EDM의 상속은 개체 지향 프로그래밍 언어의 클래스에 대한 상속과 유사합니다.  개체 지향 언어의 클래스와 마찬가지로 개념적 모델에서 다른 엔터티 형식\(*기본 형식*\)으로부터 상속되는 엔터티 형식\(*파생 형식*\)을 정의할 수 있습니다.  그러나 개체 지향 프로그래밍의 클래스와 달리 개념적 모델에서 파생 형식은 항상 기본 형식의 [속성](../../../../docs/framework/data/adonet/property.md)과 [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md)을 모두 상속합니다.  파생 형식에서 상속된 속성을 재정의할 수는 없습니다.  
  
 개념적 모델에서는 파생 형식이 다른 파생 형식으로부터 상속받는 상속 계층 구조를 작성할 수 있습니다.  계층 구조의 맨 위에 있는 형식\(파생 형식이 아닌 계층 구조의 한 형식\)을 *루트 형식*이라고 합니다.  상속 계층 구조의 루트 형식에 [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md)를 정의해야 합니다.  
  
 파생 형식이 둘 이상의 형식으로부터 상속받는 상속 계층 구조는 작성할 수 없습니다.  예를 들어, `Book` 엔터티 형식이 포함된 개념적 모델에서는 각각 `Book`으로부터 상속되는 파생 형식 `FictionBook`과 `NonFictionBook`을 정의할 수 있습니다.  그러나 `FictionBook` 및 `NonFictionBook` 형식에서 모두 상속되는 형식을 정의할 수는 없습니다.  
  
## 예제  
 다음 다이어그램에서는 네 가지 엔터티 형식 `Book`, `FictionBook`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  `FictionBook` 엔터티 형식은 `Book` 엔터티 형식에서 상속되는 파생 형식입니다.  `FictionBook` 형식은 `ISBN (Key)`, `Title` 및 `Revision` 속성을 상속하고 `Genre`라는 추가 속성을 정의합니다.  
  
 ![상속](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라는 DSL\(Domain\-Specific Language\)을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 형식에서 상속되는 엔터티 형식 `FictionBook`을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)