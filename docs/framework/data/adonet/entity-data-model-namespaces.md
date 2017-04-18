---
title: "엔터티 데이터 모델: 네임스페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# 엔터티 데이터 모델: 네임스페이스
EDM\(엔터티 데이터 모델\)의 네임스페이스는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md), [복합 형식](../../../../docs/framework/data/adonet/complex-type.md) 및 [연결](../../../../docs/framework/data/adonet/association-type.md)의 추상 컨테이너입니다.  EDM의 네임스페이스는 프로그래밍 언어의 네임스페이스와 유사하며, 포함하는 개체에 대한 컨텍스트를 제공하고 이름은 같지만 다른 네임스페이스에 포함된 개체를 구분하는 방법을 제공합니다.  
  
## 예제  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라는 DSL\(Domain\-Specific Language\)을 사용하여 개념적 모델을 정의합니다.  다음 CSDL 코드에서는 네임스페이스를 사용하여 다른 개념적 모델에서 정의된 형식을 식별합니다.  다음 예제에서는 `ExtendedBooksModel` 네임스페이스에서 가져온 복합 형식 속성\(`Address`\)이 있는 엔터티 형식\(`Publisher`\)을 정의합니다.  `Using` 요소는 네임스페이스를 가져왔음을 나타냅니다.  `Address` 속성의 형식은 정규화된 이름\(`ExtendedBooksModel.Address`\)을 사용하여 정의되며, 이 형식이 `ExtendedBooksModel` 네임스페이스에 정의되었음을 나타냅니다.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)