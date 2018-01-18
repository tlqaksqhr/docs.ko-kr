---
title: "엔터티 형식(entity type)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 9b32f188d09114cdef4327df3aa1a74a304e7c3e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="entity-type"></a>엔터티 형식(entity type)
*엔터티 형식* 는 엔터티 데이터 모델 (EDM)와 데이터의 구조를 설명 하기 위한 기본적인 빌딩 블록입니다. 개념적 모델에서 엔터티 형식은 고객이나 주문과 같은 최상위 개념의 구조를 나타냅니다. 엔터티 형식은 엔터티 형식 인스턴스의 템플릿입니다. 각 템플릿에는 다음 정보가 들어 있습니다.  
  
-   고유한 이름 (필수)  
  
-   [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 하나 이상의 속성에 의해 정의 됩니다. (필수)  
  
-   데이터 형식으로 [속성](../../../../docs/framework/data/adonet/property.md)합니다. (선택적 요소)  
  
-   [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 하나 탐색할 수 있도록 하는 [끝](../../../../docs/framework/data/adonet/association-end.md) 의 [연결](../../../../docs/framework/data/adonet/association-type.md) 다른 쪽 끝입니다. 이 매개 변수는 선택 사항입니다.  
  
 응용 프로그램에서 엔터티 형식의 인스턴스는 특정 고객 또는 주문과 같은 특정 개체를 나타냅니다. 각 엔터티 형식의 인스턴스는 고유 해야 합니다. [엔터티 키](../../../../docs/framework/data/adonet/entity-key.md) 내는 [엔터티 집합](../../../../docs/framework/data/adonet/entity-set.md)합니다.  
  
 두 엔터티 형식 인스턴스는 형식이 동일하고 해당 엔터티 키 값이 동일한 경우에만 동일한 것으로 간주됩니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 엔터티 키를 구성하는 각 엔터티 형식의 속성은 "(키)"로 표시됩니다.  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [facet](../../../../docs/framework/data/adonet/facet.md)
