---
title: "수치 연산 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 수치 연산 함수
.NET Framework Data Provider for SQL Server\(SqlClient\)에서는 인수로 제공된 입력 값에 대해 계산을 수행한 다음 숫자 값으로 된 결과를 반환하는 수치 연산 함수를 제공합니다.  이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다.  공급자의 네임스페이스 속성이 있으면 특정 구문\(예: 형식 및 함수\)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다. 다음 표에서는 SqlClient 수치 함수에 대해 설명합니다.  
  
|함수|설명|  
|--------|--------|  
|`ABS(` `expression` `)`|절대 값 함수를 수행합니다.<br /><br /> **인수**<br /><br /> `expression`: `Int32`,  `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **반환 값**<br /><br /> 지정한 식의 절대 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.ABS(-2)`|  
|`ACOS(` `expression` `)`|지정한 식의 아크코사인 값을 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.ACOS(.9)`|  
|`ASIN(` `expression` `)`|지정한 식의 아크사인 값을 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.ASIN(.9)`|  
|`ATAN(` `expression` `)`|지정한 숫자 식의 아크탄젠트 값을 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.ATAN(9)`|  
|`ATN2(` `expression`, `expression``)`|탄젠트 값이 지정한 두 숫자 식 사이에 속하는 각도를 라디안으로 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.ATN2(9, 8)`|  
|`CEILING(` `expression` `)`|지정한 식을 해당 식보다 크거나 같은 가장 작은 정수로 변환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Int32`,  `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_CEILING](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_ceiling)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]|  
|`COS(` `expression` `)`|라디안으로 지정된 각도의 삼각 코사인을 계산합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.COS(45)`|  
|`COT(` `expression` `)`|지정된 각도의 삼각 코탄젠트를 라디안으로 계산합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.COT(60)`|  
|`DEGREES(` `radians` `)`|해당 각도를 도 단위로 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Int32`,  `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.DEGREES(3.1)`|  
|`EXP(` `expression` `)`|지정한 숫자 식의 지수 값을 계산합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.EXP(1)`|  
|`FLOOR(` `expression` `)`|지정한 식을 해당 식보다 작거나 같은 가장 큰 정수로 변환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#SQLSERVER_FLOOR](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#sqlserver_floor)]
 [!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]|  
|`LOG(` `expression` `)`|지정한 `float` 식의 자연 로그를 계산합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.LOG(100)`|  
|`LOG10(` `expression` `)`|지정한 `Double` 식의 상용 로그를 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.LOG10(100)`|  
|`PI()`|파이의 상수 값을 `Double`로 반환합니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.PI()`|  
|`POWER(` `numeric_expression, power_expression` `)`|지정한 숫자 식의 지정된 거듭제곱 값을 계산합니다.<br /><br /> **인수**<br /><br /> `numeric_expression`:  `Int32`,  `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> `power_expression`: `numeric_expression`에 대해 계산할 거듭제곱을 나타내는 `Double`입니다.<br /><br /> **반환 값**<br /><br /> 지정한 `numeric_expression`에 지정한 `power_expression`을 거듭제곱한 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.POWER(2,7)`|  
|`RADIANS(` `expression` `)`|각도를 라디안으로 변환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Int32`,  `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`:  `Int64`입니다.<br /><br /> `Double` 또는<br /><br /> `Decimal`.<br /><br /> **예제**<br /><br /> `SqlServer.RADIANS(360.0)`|  
|`RAND(`\[seed\]`)`|0에서 1 사이의 임의 값을 반환합니다.<br /><br /> **인수**<br /><br /> 시드 값을 `Int32`로 반환합니다.  시드를 지정하지 않으면 SQL Server 데이터베이스 엔진에서 시드 값을 임의로 할당합니다.  지정된 특정 시드 값에 대해 반환되는 결과는 항상 동일합니다.<br /><br /> **반환 값**<br /><br /> 0에서 1 사이의 임의 `Double` 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.RAND()`|  
|`ROUND(` `numeric_expression, length` \[ ,`function` \]`)`|숫자 식을 지정한 길이나 전체 자릿수로 반올림하여 반환합니다.<br /><br /> **인수**<br /><br /> `numeric_expression`:  `Int32`,  `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> `length`: `numeric_expression`을 반올림할 전체 자릿수를 나타내는 `Int32`입니다.  `length`가 양수일 경우 `numeric_expression`은 `length`에서 지정한 소수 자릿수로 반올림됩니다.  `length`가 음수일 경우 `numeric_expression`은 `length`에서 지정한 대로 소수점의 왼쪽에서 반올림됩니다.<br /><br /> `function`: `` \(선택 사항\) 수행할 연산 형식을 나타내는 `Int32`입니다.  함수를 생략하거나 값이 0\(기본값\)일 경우 `numeric_expression` 이 반올림됩니다.  0이 아닌 값을 지정하면 `numeric_expression`이 잘립니다.<br /><br /> **반환 값**<br /><br /> 지정한 `numeric_expression`에 지정한 `power_expression`을 거듭제곱한 값입니다.<br /><br /> **예제**<br /><br /> `SqlServer.ROUND(748.58, -3)`|  
|`SIGN(` `expression` `)`|지정한 식의 양수\(\+1\), 0 또는 음수\(\-1\) 부호를 반환합니다.<br /><br /> **인수**<br /><br /> `expression`, `Int32`:  `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.<br /><br /> **예제**<br /><br /> `SqlServer.SIGN(-10)`|  
|`SIN(` `expression` `)`|라디안으로 지정한 각도의 삼각 사인을 계산하여 `Double` 식을 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.SIN(20)`|  
|`SQRT(` `expression` `)`|지정한 식의 제곱근을 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.SQRT(3600)`|  
|`SQUARE(` `expression` `)`|지정한 식의 제곱을 반환합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.SQUARE(25)`|  
|`TAN(` `expression` `)`|지정한 식의 탄젠트를 계산합니다.<br /><br /> **인수**<br /><br /> `expression`: `Double`<br /><br /> **반환 값**<br /><br /> `Double`<br /><br /> **예제**<br /><br /> `SqlServer.TAN(45.0)`|  
  
 SqlClient에서 지원하는 수치 함수에 대한 자세한 내용은 SqlClient 공급자 매니페스트에 지정한 SQL Server 버전의 설명서를 참조하세요.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[수치 연산 함수\(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkId=115913)\(영문\)|[수치 연산 함수\(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkId=115911)\(영문\)|[수치 연산 함수\(Transact\-SQL\)](http://go.microsoft.com/fwlink/?LinkId=115912)\(영문\)|  
  
## 참고 항목  
 [Entity Framework 함수용 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)