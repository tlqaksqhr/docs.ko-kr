---
title: "리터럴(Entity SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 092ef693-6e5f-41b4-b868-5b9e82928abf
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1e2f787c544550542d04a442ede7feead1613d4e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="literals-entity-sql"></a>리터럴(Entity SQL)
이 항목에서는 리터럴에 대한 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 지원을 설명합니다.  
  
## <a name="null"></a>Null  
 null 리터럴은 모든 형식의 null 값을 나타내는 데 사용됩니다. null 리터럴은 모든 형식과 호환됩니다.  
  
 형식화된 null은 null 리터럴에 대한 캐스트를 통해 만들 수 있습니다. 자세한 내용은 참조 [캐스트](../../../../../../docs/framework/data/adonet/ef/language-reference/cast-entity-sql.md)합니다.  
  
 규칙에 대 한 자유 부동 null 리터럴을 사용할 수 있습니다, 참조 [Null 리터럴 및 형식 유추](../../../../../../docs/framework/data/adonet/ef/language-reference/null-literals-and-type-inference-entity-sql.md)합니다.  
  
## <a name="boolean"></a>부울  
 Boolean 리터럴은 `true` 및 `false` 키워드로 표시됩니다.  
  
## <a name="integer"></a>Integer  
 Integer 리터럴은 <xref:System.Int32> 또는 <xref:System.Int64> 형식일 수 있습니다. <xref:System.Int32> 리터럴은 일련의 숫자입니다. <xref:System.Int64> 리터럴은 맨 뒤에 대문자 L이 오는 일련의 숫자입니다.  
  
## <a name="decimal"></a>Decimal  
 고정 소수점 수는 일련의 숫자, 점(.) 및 다른 일련의 숫자로 구성되며 맨 뒤에 대문자로 된 "M"이 포함됩니다.  
  
## <a name="float-double"></a>Float, Double  
 배정밀도 부동 소수점 수는 일련의 숫자, 점(.) 및 다른 일련의 숫자로 구성되며 맨 뒤에 지수가 포함됩니다. 단정밀도 부동 소수점 수(또는 float)는 배정밀도 부동 소수점 수 구문 뒤에 소문자 f가 포함됩니다.  
  
## <a name="string"></a>문자열  
 문자열은 따옴표로 묶인 일련의 문자입니다. 따옴표는 양쪽 모두 작은따옴표(`'`)이거나 큰따옴표(")일 수 있습니다. 문자열 리터럴은 유니코드이거나 비유니코드일 수 있습니다. 문자열 리터럴을 유니코드로 선언하려면 리터럴 앞에 대문자 "N"을 접두사로 사용합니다. 기본값은 비유니코드 문자열 리터럴입니다. N과 문자열 리터럴 페이로드 사이에는 공백을 사용할 수 없으며 N은 대문자여야 합니다.  
  
```  
'hello' -- non-Unicode character string literal  
N'hello' -- Unicode character string literal  
"x"  
N"This is a string!"  
'so is THIS'  
```  
  
## <a name="datetime"></a>DateTime  
 datetime 리터럴은 로캘과 무관하며 날짜 부분과 시간 부분으로 구성됩니다. 날짜 및 시간 부분은 모두 필수 요소이며 기본값은 없습니다.  
  
 날짜 부분에 형식 이어야 합니다.: `YYYY` - `MM` - `DD`여기서 `YYYY` 는 0001에서 9999 사이의 4 자리 연도 값 `MM` 은 1에서 12 사이의 월 및 `DD` 은 지정된 된 월에 유효한 일 값은 `MM`합니다.  
  
 시간 부분의 형식은 `HH`:`MM`[:`SS`[.fffffff]]이어야 하며, 여기서 `HH`는 0에서 23 사이의 시간 값이고, `MM`은 0에서 59 사이의 분 값이며, `SS`는 0에서 59 사이의 초 값이며, fffffff는 0에서 9999999 사이의 소수로 나타낸 초 값입니다. 모든 값 범위에서 해당 시작 값과 끝 값이 포함됩니다. 소수로 나타낸 초는 선택적 요소입니다. 소수로 나타낸 초가 지정되지 않은 경우 초를 선택하며, 이 경우 초는 필수 요소입니다. 초 또는 소수로 나타낸 초가 지정되지 않은 경우에는 기본값 0이 대신 사용됩니다.  
  
 DATETIME 기호와 리터럴 페이로드 사이에 들어갈 수 있는 공백의 수는 제한이 없지만 줄 바꿈은 허용되지 않습니다.  
  
```  
DATETIME'2006-10-1 23:11'  
DATETIME'2006-12-25 01:01:00.0000000' -- same as DATETIME'2006-12-25 01:01'  
```  
  
## <a name="time"></a>시간  
 time 리터럴은 로캘과 무관하며 시간 부분만으로 구성됩니다. 시간 부분은 필수 요소이며 기본값은 없습니다. 이 형식은 HH:MM[:SS[.fffffff]]이어야 하며, 여기서 HH는 0에서 23 사이의 시간 값이고, MM은 0에서 59 사이의 분 값이며, SS는 0에서 59 사이의 초 값이며, fffffff는 0에서 9999999 사이의 소수로 나타낸 초 값입니다. 모든 값 범위에서 해당 시작 값과 끝 값이 포함됩니다. 소수로 나타낸 초는 선택적 요소입니다. 소수로 나타낸 초가 지정되지 않은 경우 초를 선택하며, 이 경우 초는 필수 요소입니다. 초 또는 소수로 나타낸 초가 지정되지 않은 경우에는 기본값 0이 대신 사용됩니다.  
  
 TIME 기호와 리터럴 페이로드 사이에 들어갈 수 있는 공백의 수는 제한이 없지만 줄 바꿈은 허용되지 않습니다.  
  
```  
TIME‘23:11’  
TIME‘01:01:00.1234567’  
```  
  
## <a name="datetimeoffset"></a>DateTimeOffset  
 datetimeoffset 리터럴은 로캘과 무관하며 날짜 부분, 시간 부분 및 오프셋 부분으로 구성됩니다. 날짜, 시간, 오프셋 부분은 모두 필수 요소이며 기본값은 없습니다. 날짜 부분의 형식은 YYYY-MM-DD여야 하며, 여기서 YYYY는 0001에서 9999 사이의 4자리 연도 값이고, MM은 1에서 12 사이의 월이며, DD는 지정된 월에 유효한 일 값입니다. 시간 부분의 형식은 HH:MM[:SS[.fffffff]]이어야 하며, 여기서 HH는 0에서 23 사이의 시간 값이고, MM은 0에서 59 사이의 분 값이며, SS는 0에서 59 사이의 초 값이며, fffffff는 0에서 9999999 사이의 소수로 나타낸 초 값입니다. 모든 값 범위에서 해당 시작 값과 끝 값이 포함됩니다. 소수로 나타낸 초는 선택적 요소입니다. 소수로 나타낸 초가 지정되지 않은 경우 초를 선택하며, 이 경우 초는 필수 요소입니다. 초 또는 소수로 나타낸 초가 지정되지 않은 경우에는 기본값 0이 대신 사용됩니다. 오프셋된 부분의 형식 이어야 합니다. {+ &#124;-} hh: mm, HH와 MM가 시간 부분에서와 같이 의미 합니다. 하지만 오프셋의 경우 범위가 -14:00과 + 14:00 사이여야 합니다.  
  
 DATETIMEOFFSET 기호와 리터럴 페이로드 사이에 들어갈 수 있는 공백의 수는 제한이 없지만 줄 바꿈은 허용되지 않습니다.  
  
```  
DATETIMEOFFSET‘2006-10-1 23:11 +02:00’  
DATETIMEOFFSET‘2006-12-25 01:01:00.0000000 -08:30’  
```  
  
> [!NOTE]
>  유효한 Entity SQL 리터럴 값이 CLR 또는 데이터 소스에 대한 지원 범위를 벗어날 수 있으며, 이런 경우 예외가 발생할 수 있습니다.  
  
## <a name="binary"></a>이항  
 이진 문자열 리터럴은 키워드 binary 또는 바로 가기 기호 `X` 또는 `x` 뒤에 작은따옴표로 구분되는 16진수 시퀀스입니다. 바로 가기 기호인 `X`는 대소문자를 구분하지 않습니다. 키워드 `binary`와 이진 문자열 값 사이에는 하나 이상의 공백을 사용하거나 사용하지 않을 수 있습니다.  
  
 16진수 문자도 대/소문자를 구분하지 않습니다. 리터럴을 구성하는 16진수의 자릿수가 홀수인 경우 해당 리터럴의 맨 앞에 16진수 0이 추가되어 다음 짝수의 16진수에 맞춰 정렬됩니다. 이진 문자열 크기에 대한 공식적인 제한은 없습니다.  
  
```  
Binary'00ffaabb'  
X'ABCabc'  
BINARY    '0f0f0f0F0F0F0F0F0F0F'  
X'' –- empty binary string  
```  
  
## <a name="guid"></a>Guid  
 `GUID` 리터럴은 GUID(Globally Unique Identifier)를 나타냅니다. 키워드에 의해 구성 된 시퀀스는 `GUID` 리터럴은에서 16 진수 숫자가 차례로 표시 된 *레지스트리* 형식: 8-4-4-4-12 작은따옴표로 묶여 있습니다. 16진수는 대/소문자를 구분하지 않습니다.  
  
 GUID 기호와 리터럴 페이로드 사이에 들어갈 수 있는 공백의 수는 제한이 없지만 줄 바꿈은 허용되지 않습니다.  
  
```  
Guid'1afc7f5c-ffa0-4741-81cf-f12eAAb822bf'  
GUID  '1AFC7F5C-FFA0-4741-81CF-F12EAAB822BF'  
```  
  
## <a name="see-also"></a>참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
