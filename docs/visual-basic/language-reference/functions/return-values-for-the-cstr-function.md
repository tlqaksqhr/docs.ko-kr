---
title: "Return Values for the CStr Function (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "times, CStr Function return values"
  - "type conversion"
  - "dates [Visual Basic], CStr Function return values"
  - "CStr function"
  - "strings [Visual Basic], return value"
  - "Date data type, converting"
  - "dates [Visual Basic]"
  - "String data type, converting"
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Return Values for the CStr Function (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

다음 표에서는 `expression`의 여러 데이터 형식에 대한 `CStr`의 반환 값을 보여 줍니다.  
  
|`expression`의 형식|`CStr`의 반환 값|  
|----------------------|------------------|  
|[Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|"True" 또는 "False"를 포함하는 문자열|  
|[Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md)|시스템의 간단한 날짜 형식으로 된 `Date` 값\(날짜 및 시간\)을 포함하는 문자열|  
|[Numeric Data Types](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|숫자를 나타내는 문자열|  
  
## CStr 및 Date  
 `Date` 형식에는 항상 날짜 정보와 시간 정보가 모두 포함됩니다.  형식 변환을 목적으로, Visual Basic은 1\/1\/0001\(1년 1월 1일\)을 날짜의 *기본값*으로 간주하고 00:00:00\(자정\)을 시간의 기본값으로 간주합니다.  `CStr`의 결과 문자열에 중립 값을 포함하지 않습니다.  예를 들어, `#January 1, 0001 9:30:00#`을 문자열로 변환한 결과는 "9:30:00 AM"이며 날짜 정보는 표시되지 않습니다.  그러나 날짜 정보는 원래 `Date` 값에 그대로 있으며 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 등의 함수를 사용하여 복구할 수 있습니다.  
  
> [!NOTE]
>  `CStr` 함수는 응용 프로그램의 현재 문화권 설정을 기준으로 변환을 수행합니다.  특정 문화권의 숫자를 문자열로 나타내려면 해당 숫자에 `ToString(IFormatProvider)` 메서드를 사용합니다.  예를 들어, `Double` 형식의 값을 `String` 형식으로 변환할 때는 <xref:System.Double.ToString%2A?displayProperty=fullName>을 사용합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md)