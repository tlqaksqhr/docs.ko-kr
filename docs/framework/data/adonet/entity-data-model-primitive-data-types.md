---
title: "엔터티 데이터 모델: 기본 데이터 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0bfd6a1f2ab938468cc1aa02d6cf4b1eb4d7c530
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model-primitive-data-types"></a>엔터티 데이터 모델: 기본 데이터 형식
(EDM (엔터티 데이터 모델) 집합을 정의 하는 데 사용 되는 추상 기본 데이터 형식 (예: 문자열, Boolean, Int32, 및 등)을 지원 [속성](../../../../docs/framework/data/adonet/property.md) 개념적 모델에서. 이러한 기본 데이터 형식은 SQL Server 데이터베이스나 CLR(공용 언어 런타임)과 같은 저장소 또는 호스팅 환경에서 지원되는 실제 기본 데이터 형식의 프록시입니다. EDM에서는 기본 데이터 형식에 대한 작업 또는 변환의 의미 체계를 정의하지 않습니다. 이러한 의미 체계는 저장소 또는 호스팅 환경에서 정의됩니다. 일반적으로 EDM의 기본 데이터 형식은 저장소 또는 호스팅 환경에서 해당하는 기본 데이터 형식에 매핑됩니다. Entity Framework 매핑되는 방법을 EDM의 기본 형식은 SQL Server 데이터 형식에 대 한 정보를 참조 하십시오. [Entity FrameworkTypes 용 SqlClient](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)합니다.  
  
> [!NOTE]
>  EDM에서는 기본 데이터 형식 컬렉션을 지원하지 않습니다.  
  
 EDM의 구조화 된 데이터 형식에 대 한 정보를 참조 하십시오. [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 및 [복합 형식](../../../../docs/framework/data/adonet/complex-type.md)합니다.  
  
## <a name="primitive-data-types-supported-in-the-entity-data-model"></a>엔터티 데이터 모델에서 지원되는 기본 데이터 형식  
 다음 표에서는 EDM에서 지원하는 기본 데이터 형식을 보여 줍니다. 표에 나와 [패싯](../../../../docs/framework/data/adonet/facet.md) 각 기본 데이터 형식에 적용할 수 있습니다.  
  
|기본 데이터 형식|설명|적용 가능한 패싯|  
|-------------------------|-----------------|-----------------------|  
|이항|이진 데이터를 포함합니다.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|`true` 또는 `false` 값을 포함합니다.|Nullable, Default|  
|Byte|부호 없는 8비트 정수 값을 포함합니다.|Precision, Nullable, Default|  
|DateTime|날짜 및 시간을 나타냅니다.|Precision, Nullable, Default|  
|DateTimeOffset|날짜 및 시간을 GMT에서의 오프셋(분)으로 포함합니다.|Precision, Nullable, Default|  
|Decimal|고정 전체 자릿수와 소수 자릿수가 있는 숫자 값을 포함합니다.|Precision, Nullable, Default|  
|Double|전체 자릿수가 15자리인 부동 소수점 숫자를 포함합니다.|Precision, Nullable, Default|  
|Float|전체 자릿수가 7자리인 부동 소수점 숫자를 포함합니다.|Precision, Nullable, Default|  
|Guid|16바이트 고유 식별자를 포함합니다.|Precision, Nullable, Default|  
|Int16|부호 있는 16비트 정수 값을 포함합니다.|Precision, Nullable, Default|  
|Int32|부호 있는 32비트 정수 값을 포함합니다.|Precision, Nullable, Default|  
|Int64|부호 있는 64비트 정수 값을 포함합니다.|Precision, Nullable, Default|  
|SByte|부호 있는 8비트 정수 값을 포함합니다.|Precision, Nullable, Default|  
|문자열|문자 데이터를 포함합니다.|Unicode, FixedLength, MaxLength, Collation, Precision, Nullable, Default|  
|시간|시간을 포함합니다.|Precision, Nullable, Default|  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)
