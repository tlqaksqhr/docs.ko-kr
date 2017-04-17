---
title: "모델 정의 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# 모델 정의 함수
*모델 정의 함수*는 개념적 모델에 정의된 함수입니다.  모델 정의 함수의 본문은 데이터 소스에서 지원되는 규칙이나 언어에 독립적으로 함수를 표현할 수 있는 [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)로 표현됩니다.  
  
 모델 정의 함수 정의에는 다음 정보가 들어 있습니다.  
  
-   함수 이름  \(필수\)  
  
-   반환 값의 형식  이 매개 변수는 선택 사항입니다.  
  
    > [!NOTE]
    >  반환 형식을 지정하지 않으면 반환 값은 void입니다.  
  
-   매개 변수 정보  이 매개 변수는 선택 사항입니다.  
  
-   함수의 본문을 정의하는 [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) 식  
  
 모델 정의 함수는 출력 매개 변수를 지원하지 않습니다.  모델 정의 함수를 작성할 수 있도록 이러한 제한이 적용됩니다.  
  
## 예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  
  
 ![게시 날짜가 있는 모델](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)는 [CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)\(개념 스키마 정의 언어\)이라는 DSL\(Domain\-Specific Language\)을 사용하여 개념적 모델을 정의합니다.  다음 CSDL에서는 위 다이어그램의 `Book` 인스턴스가 출판된 이후의 년 수를 반환하는 함수를 개념적 모델에 정의합니다.  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)   
 [엔터티 데이터 모델: 기본 데이터 형식](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)