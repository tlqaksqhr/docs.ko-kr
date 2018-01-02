---
title: "탐색 속성(navigation property)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: dc980a2c61be736e2c1d8e52d8f13d0ea5ed09f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="navigation-property"></a>탐색 속성(navigation property)
A *탐색 속성* 은 선택적 속성에는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 하나씩 탐색할 수 있게 해 주는 [끝](../../../../docs/framework/data/adonet/association-end.md) 의 [연결](../../../../docs/framework/data/adonet/association-type.md) 를 다른 쪽 끝입니다. 다른 달리 [속성](../../../../docs/framework/data/adonet/property.md), 탐색 속성은 데이터를 전달 하지 않습니다.  
  
 탐색 속성 정의에는 다음 정보가 들어 있습니다.  
  
-   이름 (필수)  
  
-   탐색하는 연결 (필수)  
  
-   탐색하는 연결의 End (필수)  
  
 탐색 속성은 연결의 양쪽 End에 있는 엔터티 형식 모두에 대해 선택적 요소입니다. 연결의 End에 있는 한 엔터티 형식에 대해 탐색 속성을 정의하는 경우 연결의 다른 End에 있는 엔터티 형식에 대해서는 탐색 속성을 정의할 필요가 없습니다.  
  
 탐색 속성의 데이터 형식을 따라 사용자가 [복합성](../../../../docs/framework/data/adonet/association-end-multiplicity.md) 해당 원격 [연결 end](../../../../docs/framework/data/adonet/association-end.md)합니다. 예를 들어, `OrdersNavProp` 탐색 속성이 `Customer` 엔터티 형식에 존재하며 `Customer`와 `Order` 간의 일대다 연결을 탐색한다고 가정합니다. 탐색 속성에 대한 원격 연결 End의 복합성이 다수(*)이므로 해당 데이터 형식은 `Order`의 컬렉션입니다. 마찬가지로 `CustomerNavProp` 탐색 속성이 `Order` 엔터티 형식에 존재하는 경우 원격 End의 복합성이 한 개(1)이므로 해당 데이터 형식은 `Customer`가 됩니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 세 가지 엔터티 형식 `Book`, `Publisher` 및 `Author`가 포함된 개념적 모델을 보여 줍니다. 탐색 속성 `Publisher` 및 `Authors`는 Book 엔터티 형식에 정의됩니다. 탐색 속성 `Books`는 Publisher 엔터티 형식과 `Author` 엔터티 형식에 모두 정의됩니다.  
  
 ![탐색 속성이 있는 모델](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `Book` 엔터티 형식을 정의합니다.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 XML 특성을 사용하여 탐색 속성을 정의하는 데 필요한 정보를 전달합니다. `Name` 특성에는 속성 이름이 포함되고, `Relationship` 특성에는 탐색하는 연결 이름이 포함되고, `FromRole` 및 `ToRole` 특성에는 연결 End가 포함됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
