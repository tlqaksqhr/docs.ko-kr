---
title: "엔터티 컨테이너 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 엔터티 컨테이너
*엔터티 컨테이너*는 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md), [연결 집합](../../../../docs/framework/data/adonet/association-set.md) 및 [함수 가져오기](../../../../docs/framework/data/adonet/model-declared-function.md)의 논리적 그룹입니다.  
  
 개념적 모델에 정의된 엔터티 컨테이너에 대해 다음 조건이 충족되어야 합니다.  
  
-   각 개념적 모델에 엔터티 컨테이너가 하나 이상 정의되어 있어야 합니다.  
  
-   각 개념적 모델 내에서 엔터티 컨테이너의 이름이 고유해야 합니다.  
  
 엔터티 컨테이너는 하나 이상의 네임스페이스에 정의된 엔터티 형식이나 연결을 사용하는 엔터티 집합 또는 연결 집합을 정의할 수 있습니다.  자세한 내용은 [엔터티 데이터 모델: 네임스페이스](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)을 참조하세요.  
  
## 예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  자세한 내용은 다음 예제를 참조하세요.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 다이어그램에는 엔터티 컨테이너 정보가 표시되지 않지만 개념적 모델에서 엔터티 컨테이너를 정의해야 합니다.  [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라고 하는 DSL을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위의 다이어그램에 표시된 개념적 모델의 엔터티 컨테이너를 정의합니다.  엔터티 컨테이너 이름은 XML 특성에 정의되어 있습니다.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)