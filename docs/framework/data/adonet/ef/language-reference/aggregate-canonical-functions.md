---
title: "집계 정식 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 5a5aea48b1c70c550641f3450dff16e57dd4f62b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="aggregate-canonical-functions"></a>집계 정식 함수

집계는 일련의 입력 값을 단일 값으로 줄이는 식입니다. 집계는 일반적으로 SELECT 식의 GROUP BY 절과 함께 사용되며 사용할 수 있는 위치에 대한 제약 조건이 있습니다.

다음 표에서는 집계 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수를 보여 줍니다.

| 함수 | 설명 |
| -------- | ----------- |
| `Avg(expression)` | null이 아닌 값의 평균을 반환합니다.<br><br>**인수**<br><br>`Int32`, `Int64`, `Double` 및 `Decimal`입니다.<br><br>**반환 값**<br><br>`expression`의 형식입니다. 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)][!code-sql[DP EntityServices Concepts#EDM_AVG](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)] |
| `BigCount(expression)` | null 값과 중복 값을 비롯한 집계의 크기를 반환합니다.<br><br>**인수**<br><br>모든 형식입니다.<br><br>**반환 값**<br><br>`Int64`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)][!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)] |
| `Count(expression)` | null 값과 중복 값을 비롯한 집계의 크기를 반환합니다.<br><br>**인수**<br><br>모든 형식입니다.<br><br>**반환 값**<br><br>`Int32`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)][!code-sql[DP EntityServices Concepts#EDM_COUNT](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)] |
| `Max(expression)` | null이 아닌 값의 최대값을 반환합니다.<br><br>**인수**<br><br>`Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`입니다.<br><br>**반환 값**<br><br>`expression`의 형식입니다. 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)][!code-sql[DP EntityServices Concepts#EDM_MAX](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)] |
| `Min(expression)` | null이 아닌 값의 최소값을 반환합니다.<br><br>**인수**<br><br>`Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`입니다.<br><br>**반환 값**<br><br>`expression`의 형식입니다. 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)][!code-sql[DP EntityServices Concepts#EDM_MIN](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)] |
| `StDev(expression)` | null이 아닌 값의 표준 편차를 반환합니다.<br><br>**인수**<br><br>`Int32`, `Int64`, `Double`, `Decimal`입니다.<br><br>**반환 값**<br><br>`Double` 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)][!code-sql[DP EntityServices Concepts#EDM_STDEV](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)] |
| `StDevP(expression)` | 모든 값의 모집단에 대한 표준 편차를 반환합니다.<br><br>**인수**<br><br>`Int32`, `Int64`, `Double`, `Decimal`입니다.<br><br>**반환 값**<br><br>`Double` 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)][!code-sql[DP EntityServices Concepts#EDM_STDEVP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)] |
| `Sum(expression)` | null이 아닌 값의 합계를 반환합니다.<br><br>**인수**<br><br>`Int32`, `Int64`, `Double`, `Decimal`입니다.<br><br>**반환 값**<br><br>`Double` 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)][!code-sql[DP EntityServices Concepts#EDM_SUM](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)] |
| `Var(expression)` | null이 아닌 모든 값의 분산을 반환합니다.<br><br>**인수**<br><br>`Int32`, `Int64`, `Double`, `Decimal`입니다.<br><br>**반환 값**<br><br>`Double` 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)][!code-sql[DP EntityServices Concepts#EDM_VAR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)] |
| `VarP(expression)` | null이 아닌 모든 값의 모집단에 대한 분산을 반환합니다.<br><br>**인수**<br><br>`Int32`, `Int64`, `Double`, `Decimal`입니다.<br><br>**반환 값**<br><br>`Double` 모든 입력 값이 `Null` 값인 경우 `null`입니다.<br><br>**예제** [!code-csharp [DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)][!code-sql[DP EntityServices Concepts#EDM_VARP](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)] |

동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다. 자세한 내용은 참조 [엔터티 프레임 워크 함수에 대 한 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.

## <a name="collection-based-aggregates"></a>컬렉션 기반 집계

컬렉션 기반 집계(컬렉션 함수)는 컬렉션에 대해 작업을 수행하고 값을 반환합니다. 예를 들어 ORDERS가 모든 주문의 컬렉션인, 다음 식 사용 하 여 가장 빠른 운송 날짜를 계산할 수 있습니다.

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

컬렉션 기반 집계 내의 식은 현재 앰비언트 이름 결정 범위 내에서 계산됩니다.

## <a name="group-based-aggregates"></a>그룹 기반 집계

그룹 기반 집계는 GROUP BY 절에 정의된 대로 그룹에 대해 계산됩니다. 결과의 각 그룹별로 각 그룹의 요소를 집계 계산에 대한 입력으로 사용하여 개별 집계가 계산됩니다. SELECT 식에 GROUP BY 절이 사용되는 경우에는 식 이름, 집계 또는 상수를 그룹화하는 식만 프로젝션 또는 ORDER BY 절에 있을 수 있습니다.

다음 예제에서는 각 제품에 대해 주문된 평균 수량을 계산합니다.

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol 
  group by ol.Product as p
```

SELECT 식에 명시적 group by 절이 없는 그룹 기반 집계를 사용 하도록 것 같습니다. 이 경우 모든 요소가 단일 그룹으로 처리 됩니다. 상수를 기준으로 그룹화를 지정 하는 것과 같습니다. 예를 들어, 다음 식을 살펴보겠습니다.

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

이 식은 다음 식과 같습니다.

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

그룹 기반 집계 내의 식은 WHERE 절 식에 표시되는 이름 결정 범위 내에서 계산됩니다.

와 같이 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)], 그룹 기반 집계는 모두 지정할 수도 한정자 나 DISTINCT 한정자입니다. DISTINCT 한정자를 지정하면 집계가 계산되기 전에 집계 입력 컬렉션에서 중복 항목이 제거됩니다. ALL 한정자를 지정하거나 어떠한 한정자도 지정하지 않으면 중복 항목이 제거되지 않습니다.  

## <a name="see-also"></a>참고 항목

[정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
