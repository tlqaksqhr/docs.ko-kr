---
title: 날짜 및 시간 정식 함수
ms.date: 03/30/2017
ms.assetid: 9628b74f-1585-436a-b385-8b02ed0cdd63
ms.openlocfilehash: 2e97d9f174b8b4dcb3a4b3ab12a57251548333a1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32766750"
---
# <a name="date-and-time-canonical-functions"></a>날짜 및 시간 정식 함수
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]은 날짜 및 시간 정식 함수를 포함합니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서 날짜 및 시간을 표시 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 정식 함수입니다. `datetime` 이 <xref:System.DateTime> 값입니다.  
  
|함수|설명|  
|--------------|-----------------|  
|`AddNanoseconds(` `expression`, `number``)`|지정된 `number`(나노초)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddMicroseconds(` `expression`, `number``)`|지정된 `number`(마이크로초)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddMilliseconds(` `expression`, `number``)`|지정된 `number`(밀리초)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddSeconds(` `expression`, `number``)`|지정된 `number`(초)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddMinutes(` `expression`, `number``)`|지정된 `number`(분)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddHours(` `expression`, `number``)`|지정된 `number`(시간)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddDays(` `expression`, `number``)`|지정된 `number`(일)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime` 또는 `DateTimeOffset`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddMonths(` `expression`, `number``)`|지정된 `number`(월)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime` 또는 `DateTimeOffset`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`AddYears(` `expression`, `number``)`|지정된 `number`(연도)를 `expression`에 추가합니다.<br /><br /> **인수**<br /><br /> `expression`: `DateTime` 또는 `DateTimeOffset`입니다.<br /><br /> `number`: `Int32`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`CreateDateTime(` `year`, `month`, `day`, `hour`, `minute`, `second``)`|새 `DateTime` 값을 서버 시간대의 서버 현재 날짜 및 시간으로 반환합니다.<br /><br /> **인수**<br /><br /> `year`, `month`, `day`, `hour`, `minute`: `Int16` 및 `Int32`입니다.<br /><br /> `second`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `DateTime`|  
|`CreateDateTimeOffset(` `year`, `month`, `day`, `hour`, `minute`, `second`, `tzoffset``)`|새 `DateTimeOffset` 값을 UTC(Coordinated Universal Time)에 상대적인 서버 현재 날짜 및 시간으로 반환합니다.<br /><br /> **인수**<br /><br /> `year`, `month`, `day`, `hour`, `minute`, `tzoffset`: `Int32`입니다.<br /><br /> `second`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `DateTimeOffset`|  
|`CreateTime(` `hour`, `minute`, `second``)`|새 `Time` 값을 현재 시간으로 반환합니다.<br /><br /> **인수**<br /><br /> `hour` 및 `minute`: `Int32`입니다.<br /><br /> `second`: `Double`입니다.<br /><br /> **반환 값**<br /><br /> `Time`|  
|`CurrentDateTime()`|`DateTime` 값을 서버 시간대의 서버 현재 날짜 및 시간으로 반환합니다.<br /><br /> **반환 값**<br /><br /> `DateTime`|  
|`CurrentDateTimeOffset()`|현재 날짜, 시간 및 오프셋을 `DateTimeOffset`으로 반환합니다.<br /><br /> **반환 값**<br /><br /> `DateTimeOffset`|  
|`CurrentUtcDateTime()`|<xref:System.DateTime> 값을 UTS 시간대의 서버 현재 날짜 및 시간 형태로 반환합니다.<br /><br /> **반환 값**<br /><br /> `DateTime`|  
|`Day(` `expression` `)`|`expression`의 일 부분을 1에서 31 사이의 `Int32`로 반환합니다.<br /><br /> **인수**<br /><br /> `DateTime` 및 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 12.`<br /><br /> `Day(cast('03/12/1998' as DateTime))`|  
|`DayOfYear(` `expression` `)`|`expression`의 일 부분을 1에서 366 사이의 `Int32`로 반환합니다. 여기서 366은 윤년의 마지막 날에 대해 반환됩니다.<br /><br /> **인수**<br /><br /> `DateTime` 또는 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffNanoseconds(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(나노초)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffMilliseconds(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(밀리초)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffMicroseconds(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(마이크로초)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffSeconds(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(초)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffMinutes(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(분)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffHours(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(시간)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`, `endExpression`: `DateTime`, `DateTimeOffset` 또는 `Time`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffDays(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(일)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`: `endExpression`, `DateTime` 또는 `DateTimeOffset`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffMonths(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(월)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`: `endExpression`, `DateTime` 또는 `DateTimeOffset`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`DiffYears(` `startExpression`, `endExpression``)`|`startExpression`과 `endExpression`의 차(연도)를 반환합니다.<br /><br /> **인수**<br /><br /> `startExpression`: `endExpression`, `DateTime` 또는 `DateTimeOffset`입니다. **참고:** `startExpression` 및 `endExpression` 동일한 형식 이어야 합니다.   <br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`GetTotalOffsetMinutes(` `datetimeoffset` `)`|GMT에서 `datetimeoffset`을 차감한 시간(분)을 반환합니다. 이 값은 일반적으로 +780에서 -780(+13시간에서 -13시간) 사이입니다. **참고:** SQL Server 2008에만이 함수는 지원 합니다. <br /><br /> **인수**<br /><br /> `DateTimeOffset`<br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`Hour (` `expression` `)`|`expression`의 시간 부분을 0에서 23 사이의 `Int32`로 반환합니다.<br /><br /> **인수**<br /><br /> `DateTime, Time` 및 `DateTimeOffset`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 22.`<br /><br /> `Hour(cast('22:35:5' as DateTime))`|  
|`Millisecond(` `expression` `)`|`expression`의 밀리초 부분을 0에서 999 사이의 `Int32`로 반환합니다.<br /><br /> **인수**<br /><br /> `DateTime, Time` 및 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.|  
|`Minute(` `expression` `)`|`expression`의 분 부분을 0에서 59 사이의 `Int32`로 반환합니다.<br /><br /> **인수**<br /><br /> `DateTime, Time` 또는 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 35`<br /><br /> `Minute(cast('22:35:5' as DateTime))`|  
|`Month` `(` `expression` `)`|`expression`의 월 부분을 1에서 12 사이의 `Int32`로 반환합니다.<br /><br /> **인수**<br /><br /> `DateTime` 또는 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 3.`<br /><br /> `Month(cast('03/12/1998' as DateTime))`|  
|`Second(` `expression` `)`|`expression`의 초 부분을 0에서 59 사이의 `Int32`로 반환합니다.<br /><br /> **인수**<br /><br /> `DateTime, Time` 및 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 5`<br /><br /> `Second(cast('22:35:5' as DateTime))`|  
|`TruncateTime(` `expression` `)`|시간 값이 잘린 `expression`을 반환합니다.<br /><br /> **인수**<br /><br /> `DateTime` 또는 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `expression`의 형식입니다.|  
|`Year(` `expression` `)`|연도 부분을 반환 `expression` 로 `Int32``YYYY`합니다.<br /><br /> **인수**<br /><br /> `DateTime` 및 `DateTimeOffset`입니다.<br /><br /> **반환 값**<br /><br /> `Int32`입니다.<br /><br /> **예제**<br /><br /> `-- The following example returns 1998.`<br /><br /> `Year(cast('03/12/1998' as DateTime))`|  
  
 이러한 함수는 `null`이 입력되면 `null`을 반환합니다.  
  
 동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다. 자세한 내용은 참조 [엔터티 프레임 워크 함수에 대 한 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [정식 함수](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
