---
title: "모델 선언 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 37c6b04fbea69f62aaf7bc148ee04ace5a5a349c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="model-declared-function"></a>모델 선언 함수
A *모델 선언 함수* 개념적 모델에서 선언 되었지만 해당 개념적 모델에 정의 되지 않은 하는 함수입니다. 호스팅 또는 저장소 환경에서 함수를 정의할 수도 있습니다. 예를 들어, 모델 선언 함수를 데이터베이스에 정의된 함수에 매핑하여 개념적 모델에 서버 쪽 기능을 노출할 수 있습니다.  
  
 모델 선언 함수의 선언에는 다음 정보가 들어 있습니다.  
  
-   함수의 이름. (필수)  
  
-   반환 값의 형식 이 매개 변수는 선택 사항입니다.  
  
    > [!NOTE]
    >  반환 값을 지정하지 않으면 반환 형식은 void입니다.  
  
-   매개 변수 이름과 형식을 포함하는 매개 변수 정보 이 매개 변수는 선택 사항입니다.  
  
## <a name="example"></a>예  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) 개념 스키마 정의 언어를 호출 하는 도메인 특정 언어 DSL ()를 사용 하 여 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 개념적 모델을 정의 합니다. CSDL에서 모델 선언 함수의 구현 하는 하나는 한 [함수 가져오기](http://msdn.microsoft.com/library/125704ae-56c7-4233-80b7-389a10f3a65d)합니다. 다음 CSDL에서는 함수 가져오기 정의를 사용하여 엔터티 컨테이너를 정의합니다. 반환 형식을 지정하지 않았으므로 함수의 반환 형식은 void입니다.  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
