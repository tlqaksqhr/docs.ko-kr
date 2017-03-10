---
title: "Type Characters (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "&H prefix for hexadecimal values"
  - "hexadecimal literals"
  - "F literal type character"
  - "& identifier type character"
  - "type characters"
  - "octal literals"
  - "literals, hexadecimal"
  - "&O prefix for octal values"
  - "literals, default types"
  - "defaults, literal types"
  - "C literal type character"
  - "type characters, literal"
  - "$ identifier type character"
  - "L literal type character"
  - "UI literal type characters"
  - "default literal types"
  - "D literal type character"
  - "literals, octal"
  - "S literal type character"
  - "! identifier type character"
  - "US literal type characters"
  - "% identifier type character"
  - "data types [Visual Basic], type characters"
  - "characters, identifier type"
  - "type characters, identifier"
  - "# identifier type character"
  - "identifier type characters"
  - "literal type characters"
  - "I literal type character"
  - "R literal type character"
  - "@ identifier type character"
  - "UL literal type characters"
  - "literal types, default"
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Type Characters (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선언문에서 데이터 형식을 지정하는 것과 함께 *형식 문자*를 사용하여 일부 프로그래밍 요소의 데이터 형식을 사용할 수 있습니다.  형식 문자는 요소 바로 뒤에 나와야 하며 중간에 어떤 종류의 문자도 포함되면 안 됩니다.  
  
 형식 문자는 요소의 이름 부분이 아닙니다.  형식 문자를 사용하여 정의된 요소는 형식 문자 없이 참조될 수 있습니다.  
  
## 식별자 형식 문자  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 선언에서 변수나 상수의 데이터 형식을 지정하는 데 사용할 수 있는 *식별자 형식 문자* 집합을 제공합니다.  다음 표에서는 사용할 수 있는 식별자 데이터 형식과 사용 예제를 보여 줍니다.  
  
|식별자 형식 문자|데이터 형식|예제|  
|---------------|------------|--------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong` 또는 `UShort` 데이터 형식이나 배열 또는 구조체 등의 복합 데이터 형식에는 해당하는 식별자 형식 문자가 없습니다.  
  
 일부 경우에는 `$` 문자를 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 함수에 추가할 수 있습니다. 예를 들어, `Left` 대신 `Left$`를 사용하여 `String` 형식의 반환 값을 가져올 수 있습니다.  
  
 식별자 형식 문자는 항상 식별자 이름 바로 뒤에 나와야 합니다.  
  
## 리터럴 형식 문자  
 *리터럴*은 데이터 형식의 특정 값을 텍스트로 나타낸 것입니다.  
  
### 기본 리터럴 형식  
 코드에서 리터럴 형태가 나타나는 경우 대개 리터럴의 데이터 형식을 결정합니다.  다음 표에서는 이 기본 형식을 보여 줍니다.  
  
|리터럴의 텍스트 형태|기본 데이터 형식|예제|  
|-----------------|---------------|--------|  
|숫자\(소수 부분 없음\)|`Integer`|`2147483647`|  
|숫자\(소수 부분 없음, `Integer`에 비해 너무 큼\)|`Long`|`2147483648`|  
|숫자\(소수 부분 있음\)|`Double`|`1.2`|  
|큰따옴표로 묶임|`String`|`"A"`|  
|숫자 기호로 묶임|`Date`|`#5/17/1993 9:32 AM#`|  
  
### 강제 리터럴 형식  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 리터럴이 리터럴 형태가 나타내는 것과 다른 데이터 형식을 취하도록 하는 데 사용할 수 있는 *리터럴 형식 문자* 집합을 제공합니다.  이렇게 하려면 리터럴의 끝에 문자를 추가합니다.  다음 표에서는 사용할 수 있는 리터럴 형식 문자와 사용 예제를 보여 줍니다.  
  
|리터럴 문자 형식|데이터 형식|예제|  
|---------------|------------|--------|  
|`S`|`Short`|`I = 347S`|  
|`I`|`Integer`|`J = 347I`|  
|`L`|`Long`|`K = 347L`|  
|`D`|`Decimal`|`X = 347D`|  
|`F`|`Single`|`Y = 347F`|  
|`R`|`Double`|`Z = 347R`|  
|`US`|`UShort`|`L = 347US`|  
|`UI`|`UInteger`|`M = 347UI`|  
|`UL`|`ULong`|`N = 347UL`|  
|`C`|`Char`|`Q = "."C`|  
  
 `Boolean`, `Byte`, `Date`, `Object`, `SByte` 또는 `String` 데이터 형식이나 배열 또는 구조체 등의 복합 데이터 형식에는 해당하는 리터럴 형식 문자가 없습니다.  
  
 리터럴은 변수, 상수 및 식처럼 식별자 형식 문자\(`%`, `&`, `@`, `!`, `#`, `$`\)를 사용할 수도 있습니다.  그러나 리터럴 형식 문자\(`S`, `I`, `L`, `D`, `F`, `R`, `C`\)는 리터럴에만 사용할 수 있습니다.  
  
 리터럴 형식 문자는 항상 리터럴 값 다음에 나와야 합니다.  
  
## 16진 및 8진 리터럴  
 컴파일러에서는 대개 정수 리터럴을 10진수로 해석합니다.  정수 리터럴을 `&H` 접두사를 사용하여 16진수로 나타내고 `&O` 접두사를 사용하여 8진수로 나타낼 수 있습니다.  접두사 뒤의 숫자는 해당 숫자 체계에 적합해야 합니다.  다음 표에서는 날짜 및 시간 표시의 예를 보여 줍니다.  
  
|숫자 체계\(진법\)|접두사|유효한 숫자 값|예제|  
|-----------------|---------|--------------|--------|  
|16진수|`&H`|0\-9 및 A\-F|`&HFFFF`|  
|8진수|`&O`|0\-7|`&O77`|  
  
 접두사가 붙은 리터럴 뒤에 리터럴 형식 문자를 추가할 수 있습니다.  다음 예제에서는 이러한 방법을 보여 줍니다.  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 위 예제에서 `counter`는 10진수 값 \-32768을 갖고 `flags`는 10진수 값 \+32768을 갖습니다.  
  
## 참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)