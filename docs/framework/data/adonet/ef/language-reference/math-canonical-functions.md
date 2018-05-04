---
title: 수학 정식 함수
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 9d823eb45babca4b8f5dd717b4fb92c1984d1c8c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="math-canonical-functions"></a>수학 정식 함수
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]에는 수식 정식 함수가 포함됩니다.  
  
 다음 표에서는 수식 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수를 보여 줍니다.  
  
|함수|설명|  
|--------------|-----------------|  
|`Abs(` `value` `)`|`value`의 절대값을 반환합니다.<br /><br /> **인수**<br /><br /> `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, 및 `Decimal`합니다.<br /><br /> **반환 값**<br /><br /> `value`의 형식입니다.<br /><br /> **예제**<br /><br /> `Abs(-2)`|  
|`Ceiling(` `value` `)`|`value`보다 작지 않은 가장 작은 정수를 반환합니다.<br /><br /> **인수**<br /><br /> A `Single`, `Double`, 및 `Decimal`합니다.<br /><br /> **반환 값**<br /><br /> `value`의 형식입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
 [!code-sql[DP EntityServices Concepts#EDM_CEILING](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]|  
|`Floor(` `value` `)`|`value`보다 크지 않은 가장 큰 정수를 반환합니다.<br /><br /> **인수**<br /><br /> A `Single`, `Double`, 및 `Decimal`합니다.<br /><br /> **반환 값**<br /><br /> `value`의 형식입니다.<br /><br /> **예제**<br /><br /> [!code-csharp[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
 [!code-sql[DP EntityServices Concepts#EDM_FLOOR](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]|  
|`Power(` `value`, `exponent``)`|지정된 `value`에 대해 지정된 `exponent`의 결과를 반환합니다.<br /><br /> **인수**<br /><br /> `value`: `Int32, Int64, Double`, 또는 `Decimal`합니다.<br /><br /> `exponent`: `Int64``, Double`, 또는 `Decimal`합니다.<br /><br /> **반환 값**<br /><br /> `value`의 형식입니다.<br /><br /> **예제**<br /><br /> `Power(748.58,2)`|  
|`Round(` `value` `)`|`value`의 정수 부분을 가장 가까운 정수로 반올림하여 반환합니다.<br /><br /> **인수**<br /><br /> A `Single`, `Double`, 및 `Decimal`합니다.<br /><br /> **반환 값**<br /><br /> `value`의 형식입니다.<br /><br /> **예제**<br /><br /> `Round(748.58)`|  
|`Round(` `value`, `digits``)`|`value`를 지정된 `digits` 중 가장 가까운 숫자로 반올림하여 반환합니다.<br /><br /> **인수**<br /><br /> `value`: `Double` 또는 `Decimal`입니다.<br /><br /> `digits`: `Int16` 또는 `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `value`의 형식입니다.<br /><br /> **예제**<br /><br /> `Round(748.58,1)`|  
|`Truncate(` `value`, `digits``)`|`value`를 지정된 `digits` 중 가장 가까운 숫자로 잘라 반환합니다.<br /><br /> **인수**<br /><br /> `value`: `Double` 또는 `Decimal`입니다.<br /><br /> `digits`: `Int16` 또는 `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `value`의 형식입니다.<br /><br /> **예제**<br /><br /> `Truncate(748.58,1)`|  
  
 이러한 함수는 `null`이 입력되면 `null`을 반환합니다.  
  
 동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다. 자세한 내용은 참조 [엔터티 프레임 워크 함수에 대 한 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
