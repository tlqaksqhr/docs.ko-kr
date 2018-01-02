---
title: "연결 End"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c345213-0296-4d90-ac6d-cef179798a75
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 53e52a09533f3e1ead240ec3284371603c82ce53
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="association-end"></a>연결 End
*연결 end* 식별 하는 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 의 한쪽 끝에는 [연결](../../../../docs/framework/data/adonet/association-type.md) 및 엔터티 수는 연결의 해당 end에 있을 수 있는 인스턴스를 입력 합니다. 연결 End는 연결의 일부로 정의되고 연결에는 정확히 두 개의 연결 End가 있어야 합니다. [탐색 속성](../../../../docs/framework/data/adonet/navigation-property.md) 다른 연결의 한 end에서 탐색할 수 있도록 합니다.  
  
 연결 End 정의에는 다음 정보가 들어 있습니다.  
  
-   연결과 관련된 엔터티 형식 중 하나 (필수)  
  
    > [!NOTE]
    >  지정된 연결에서 각 연결 End에 지정한 엔터티 형식은 달라야 합니다. 이렇게 하면 자체 연결이 만들어집니다.  
  
-   [연결 end 복합성](../../../../docs/framework/data/adonet/association-end-multiplicity.md) 는 association의 한 end에 있을 수 있는 엔터티 형식 인스턴스 수를 나타내는입니다. 연결 End의 복합성 값은 한 개(1), 0개 또는 한 개(0..1) 또는 다수(*)일 수 있습니다.  
  
-   연결 End의 이름. 이 매개 변수는 선택 사항입니다.  
  
-   삭제 시 계단식 배열과 같이 연결에서 수행되는 작업에 대한 정보 이 매개 변수는 선택 사항입니다.  
  
## <a name="example"></a>예제  
 다음 다이어그램에서는 두 연결 `PublishedBy` 및 `WrittenBy`의 개념적 모델을 보여 줍니다. `PublishedBy` 연결의 연결 End는 `Book` 및 `Publisher` 엔터티 형식입니다. `Publisher` 끝의 복합성은 한 개(1)이고 `Book` 끝의 복합성은 다수(*)이므로 한 명의 발행자가 많은 책을 출판하고 책 하나는 한 명의 발행자에 의해 출판됨을 나타냅니다.  
  
 ![예제 모델](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 ADO.NET Entity Framework 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. 다음 CSDL에서는 위의 다이어그램에 표시된 `PublishedBy` 연결을 정의합니다. 각 연결 End의 형식, 이름 및 복합성은 XML 특성(각각 `Type`, `Role` 및 `Multiplicity` 특성)으로 지정됩니다. 한 End에서 수행되는 작업에 대한 선택적 정보는 XML 요소(`OnDelete` 요소)에 지정됩니다. 이 경우 발행자를 삭제하면 연결된 책도 모두 삭제됩니다.  
  
 [!code-xml[EDM_Example_Model#AssociationEnd](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#associationend)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
