---
title: 집계 함수(Entity Framework용 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 558e9f8480dd69e2277603e9bb1013acfbc29467
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32763399"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a>집계 함수(Entity Framework용 SqlClient)
.NET Framework Data Provider for SQL Server(SqlClient)에서는 집계 함수를 제공합니다. 집계 함수는 입력 값 집합에 대해 계산을 수행하여 하나의 값을 반환합니다. 이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다. 공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.  
  
 다음 표에서는 SqlClient 집계 함수를 보여 줍니다.  
  
|함수|설명|  
|--------------|-----------------|  
|`AVG(` `expression` `)`|컬렉션에 포함된 값의 평균을 반환합니다.<br /><br /> Null 값은 무시됩니다.<br /><br /> **인수**<br /><br /> `Int32`, `Int64`, `Double` 및 `Decimal`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_avg)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]|  
|`CHECKSUM_AGG(` `collection` `)`|컬렉션에 있는 값의 체크섬을 반환합니다.<br /><br /> Null 값은 무시됩니다.<br /><br /> **인수**<br /><br /> 컬렉션(`Int32`)입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_checksum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]|  
|`COUNT(` `expression` `)`|컬렉션의 항목 수를 `Int32`로 반환합니다.<br /><br /> **인수**<br /><br /> Collection(T)이며 여기서 T는<br /><br /> `Guid`(SQL Server 2000에서는 반환되지 않음),<br /><br /> `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` 또는 `Binary`<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_count)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]|  
|`COUNT_BIG(` `expression` `)`|컬렉션의 항목 수를 `bigint`로 반환합니다.<br /><br /> **인수**<br /><br /> Collection(T)이며 여기서 T는<br /><br /> `Guid`(SQL Server 2000에서는 반환되지 않음), `Boolean`, `Double`, `DateTime`, `DateTimeOffset`, `Time`, `String` 또는 `Binary`<br /><br /> **반환 값**<br /><br /> `Int64`입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_countbig)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]|  
|`MAX(` `expression` `)`|컬렉션의 최대값을 반환합니다.<br /><br /> **인수**<br /><br /> 컬렉션(T)이며, 여기서 T는 `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary` 형식 중 하나입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_max)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]|  
|`MIN(` `expression` `)`|컬렉션의 최소값을 반환합니다.<br /><br /> **인수**<br /><br /> 컬렉션(T)이며, 여기서 T는 `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String` 형식 중 하나입니다.<br /><br /> `Binary`.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_min)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]|  
|`STDEV(` `expression` `)`|지정한 식의 모든 값에 대한 통계적 표준 편차를 반환합니다.<br /><br /> **인수**<br /><br /> 컬렉션(`Double`)입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdev)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]|  
|`STDEVP(` `expression` `)`|지정한 식에 있는 모든 값의 모집단에 대한 통계적 표준 편차를 반환합니다.<br /><br /> **인수**<br /><br /> 컬렉션(`Double`)입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_stdevp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]|  
|`SUM(` `expression` `)`|컬렉션에 있는 모든 값의 합계를 반환합니다.<br /><br /> **인수**<br /><br /> 컬렉션(T)이며, 여기서 T는 `Int32`, `Int64`, `Double`, `Decimal` 형식 중 하나입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_sum)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]|  
|`VAR(` `expression` `)`|지정한 식에 있는 모든 값의 통계적 분산을 반환합니다.<br /><br /> **인수**<br /><br /> 컬렉션(`Double`)입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_var)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]|  
|`VARP(` `expression` `)`|지정한 식에 있는 모든 값의 모집단에 대한 통계적 분산을 반환합니다.<br /><br /> **인수**<br /><br /> 컬렉션(`Double`)입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_varp)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]|  
  
 SqlClient에서 지원하는 집계 함수에 대한 자세한 내용은 SqlClient 공급자 매니페스트에 지정한 SQL Server 버전의 설명서를 참조하세요.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[집계 함수 (Transact SQL)](http://go.microsoft.com/fwlink/?LinkId=115906)|[집계 함수 (Transact SQL)](http://go.microsoft.com/fwlink/?LinkID=115903)|[집계 함수 (Transact SQL)](http://go.microsoft.com/fwlink/?LinkId=115907)|  
  
## <a name="see-also"></a>참고 항목  
 [Entity SQL 언어](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [집계 정식 함수](../../../../../docs/framework/data/adonet/ef/language-reference/aggregate-canonical-functions.md)
