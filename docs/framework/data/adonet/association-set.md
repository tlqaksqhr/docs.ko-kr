---
title: "연결 집합 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 연결 집합
*연결 집합*은 같은 형식의 [연결](../../../../docs/framework/data/adonet/association-type.md) 인스턴스에 대한 논리적 컨테이너입니다.  연결 집합은 데이터 모델링 구문이 아니므로 데이터 또는 관계의 구조를 설명하지 않습니다.  대신 연결 집합은 연결 인스턴스를 그룹화하여 데이터 저장소에 매핑할 수 있도록 호스팅 또는 저장소 환경\(예: 공용 언어 런타임 또는 SQL Server 데이터베이스\)에 대한 구문을 제공합니다.  
  
 연결 집합은 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md) 및 연결 집합의 논리적 그룹인 [엔터티 컨테이너](../../../../docs/framework/data/adonet/entity-container.md) 내에서 정의됩니다.  
  
 연결 집합 정의에는 다음 정보가 들어 있습니다.  
  
-   연결 집합 이름  \(필수\)  
  
-   연결 집합에 인스턴스가 포함될 연결  \(필수\)  
  
-   두 개의 [연결 집합 End](../../../../docs/framework/data/adonet/association-set-end.md)  
  
## 예제  
 다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다.  연결 집합에 대한 정보는 다이어그램에 표시되지 않지만 다음 다이어그램에서는 이 모델을 기반으로 하여 연결 집합 및 엔터티 집합의 예제를 보여 줍니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 다음 예제에서는 위에 표시된 개념적 모델을 기반으로 하여 연결 집합\(`PublishedBy`\) 및 엔터티 집합 두 개\(`Books` 및 `Publishers`\)를 보여 줍니다.  `Books` 엔터티 집합에 있는 Bi는 런타임 시 `Book` 엔터티 형식의 인스턴스를 나타냅니다.  마찬가지로 Pj는 `Publishers` 엔터티 집합의 `Publisher` 인스턴스를 나타냅니다.  BiPj는 `PublishedBy` 연결 집합의 `PublishedBy` 연결 인스턴스를 나타냅니다.  
  
 ![예제 설정](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라는 DSL\(Domain\-Specific Language\)을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위의 다이어그램에 있는 각 연결에 대한 하나의 연결 집합을 사용하여 엔터티 컨테이너를 정의합니다.  각 연결 집합의 이름과 연결은 XML 특성을 사용하여 정의됩니다.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 두 연결 집합이 [연결 집합 End](../../../../docs/framework/data/adonet/association-set-end.md)를 공유하지만 않으면 연결당 연결 집합을 여러 개 정의할 수 있습니다.  다음 CSDL에서는 `WrittenBy` 연결에 대한 두 개의 연결 집합이 있는 엔터티 컨테이너를 정의합니다.  `Book` 및 `Author` 엔터티 형식에 대해 엔터티 집합이 여러 개 정의되었으며 어떤 연결 집합도 연결 집합 End를 공유하지 않습니다.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [외래 키 속성](../../../../docs/framework/data/adonet/foreign-key-property.md)