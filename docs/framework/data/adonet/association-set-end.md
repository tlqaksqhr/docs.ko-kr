---
title: "연결 집합 End | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 연결 집합 End
*연결 집합 End*는 [연결 집합](../../../../docs/framework/data/adonet/association-set.md) End에 있는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 및 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md)을 식별합니다.  연결 집합 End는 연결 집합의 일부로 정의되고 연결 집합에는 정확히 두 개의 연결 집합 End가 있어야 합니다.  
  
 연결 집합 End 정의에는 다음 정보가 들어 있습니다.  
  
-   연결 집합과 관련된 엔터티 형식 중 하나  \(필수\)  
  
-   연결 집합과 관련된 엔터티 형식에 대한 엔터티 집합  \(필수\)  
  
## 예제  
 다음 다이어그램에서는 두 연결 `WrittenBy` 및 `PublishedBy`의 개념적 모델을 보여 줍니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 다음 다이어그램에서는 위에 나온 개념적 모델을 기반으로 하여 하나의 연결 집합\(`PublishedBy`\) 및 두 개의 엔터티 집합\(`Books` 및 `Publishers`\)을 보여 줍니다.  연결 집합 End는 `Books` 및 `Publishers` 엔터티 집합입니다.  `Books` 엔터티 집합에 있는 Bi는 런타임 시 `Book` 엔터티 형식의 인스턴스를 나타냅니다.  마찬가지로 Pj는 `Publishers` 엔터티 집합의 `Publisher` 인스턴스를 나타냅니다.  BiPj는 `PublishedBy` 연결 집합의 `PublishedBy` 연결 인스턴스를 나타냅니다.  
  
 ![예제 설정](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라고 하는 DSL을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위의 다이어그램에 있는 각 연결에 대한 하나의 연결 집합을 사용하여 엔터티 컨테이너를 정의합니다.  연결 집합 End는 각 연결 집합 정의의 일부로 정의되어 있습니다.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)