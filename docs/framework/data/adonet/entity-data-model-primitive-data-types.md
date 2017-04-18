---
title: "엔터티 데이터 모델: 기본 데이터 형식 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7635168e-0566-4fdd-8391-7941b0d9f787
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 엔터티 데이터 모델: 기본 데이터 형식
EDM\(엔터티 데이터 모델\)에서는 개념적 모델에서 [속성](../../../../docs/framework/data/adonet/property.md)을 정의하는 데 사용되는 추상 기본 데이터 형식\(예: String, Boolean, Int32 등\) 집합을 지원합니다.  이러한 기본 데이터 형식은 SQL Server 데이터베이스나 CLR\(공용 언어 런타임\)과 같은 저장소 또는 호스팅 환경에서 지원되는 실제 기본 데이터 형식의 프록시입니다.  EDM에서는 기본 데이터 형식에 대한 작업 또는 변환의 의미 체계를 정의하지 않습니다. 이러한 의미 체계는 저장소 또는 호스팅 환경에서 정의됩니다.  일반적으로 EDM의 기본 데이터 형식은 저장소 또는 호스팅 환경에서 해당하는 기본 데이터 형식에 매핑됩니다.  Entity Framework에서 EDM의 기본 형식을 SQL Server 데이터 형식에 매핑하는 방식에 대한 자세한 내용은 [Entity FrameworkTypes용 SqlClient](../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)를 참조하세요.  
  
> [!NOTE]
>  EDM에서는 기본 데이터 형식 컬렉션을 지원하지 않습니다.  
  
 EDM의 구조적 데이터 형식에 대한 자세한 내용은 [엔터티 형식](../../../../docs/framework/data/adonet/entity-type.md) 및 [복합 형식](../../../../docs/framework/data/adonet/complex-type.md)을 참조하세요.  
  
## 엔터티 데이터 모델에서 지원되는 기본 데이터 형식  
 다음 표에서는 EDM에서 지원하는 기본 데이터 형식을 보여 줍니다.  또한 각 기본 데이터 형식에 적용할 수 있는 [패싯](../../../../docs/framework/data/adonet/facet.md)을 보여 줍니다.  
  
|기본 데이터 형식|설명|적용 가능한 패싯|  
|---------------|--------|---------------|  
|이항|이진 데이터를 포함합니다.|MaxLength, FixedLength, Nullable, Default|  
|Boolean|`true` 또는 `false` 값을 포함합니다.|Nullable, Default|  
|Byte|부호 없는 8비트 정수 값을 포함합니다.|Precision, Nullable, Default|  
|DateTime|날짜 및 시간을 나타냅니다.|Precision, Nullable, Default|  
|DateTimeOffset|날짜 및 시간을 GMT에서의 오프셋\(분\)으로 포함합니다.|Precision, Nullable, Default|  
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
  
## 참고 항목  
 [엔터티 데이터 모델의 주요 개념](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)   
 [엔터티 데이터 모델](../../../../docs/framework/data/adonet/entity-data-model.md)