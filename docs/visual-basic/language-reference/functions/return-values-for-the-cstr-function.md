---
title: "CStr 함수의 반환 값(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b498c9b1b7916467c96ed2c645c7131192a5e8b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>CStr 함수의 반환 값(Visual Basic)
다음 표에서 반환 값에 대 한 설명 `CStr` 의 서로 다른 데이터 형식에 대 한 `expression`합니다.  
  
|경우 `expression` 형식이|`CStr`반환|  
|-----------------------------|--------------------|  
|[Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|"True"를 포함 하는 문자열 또는 "False"입니다.|  
|[Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)|포함 하는 문자열을 `Date` 시스템의 간단한 날짜 형식 값 (날짜 및 시간)입니다.|  
|[숫자 데이터 형식](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|수를 나타내는 문자열입니다.|  
  
## <a name="cstr-and-date"></a>CStr 및 날짜  
 `Date` 형식이 항상 날짜와 시간 정보를 포함 합니다. 형식 변환을 위해 Visual Basic 간주 1/1/0001 (1 1 년 1 월)는 *기본값으로* 시간에 대 한 기본값으로 간주 00시: 00 (자정) 및 날짜,입니다. `CStr`결과 문자열에는 기본값이 포함 되지 않습니다. 예를 들어, 변환 하면 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00" 하 고 날짜 정보는 표시 되지 않습니다. 그러나 날짜 정보에에서는 아직 있는 원래 `Date` 값 및와 같은 함수를 사용 하 여 복구할 수 수 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>합니다.  
  
> [!NOTE]
>  `CStr` 함수 응용 프로그램에 대 한 현재 문화권 설정에 따라으로 변환을 수행 합니다. 숫자의를 사용 하 여 숫자의 문자열 표현을 특정 문화권을 가져오려면 `ToString(IFormatProvider)` 메서드. 사용 예를 들어 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환할 때 `Double` 에 `String`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Date 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md)
