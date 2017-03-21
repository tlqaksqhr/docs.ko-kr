---
title: "문자 (Visual Basic)를 입력 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- '&H prefix for hexadecimal values'
- hexadecimal literals
- F literal type character
- '& identifier type character'
- type characters
- octal literals
- literals, hexadecimal
- '&O prefix for octal values'
- literals, default types
- defaults, literal types
- C literal type character
- type characters, literal
- $ identifier type character
- L literal type character
- UI literal type characters
- default literal types
- D literal type character
- literals, octal
- S literal type character
- '! identifier type character'
- US literal type characters
- '% identifier type character'
- data types [Visual Basic], type characters
- characters, identifier type
- type characters, identifier
- '# identifier type character'
- identifier type characters
- literal type characters
- I literal type character
- R literal type character
- '@ identifier type character'
- UL literal type characters
- literal types, default
ms.assetid: 6353cb9b-6ee4-4af6-a5a8-88ce39f90cc5
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6e112e7d221ef8e7a660094306bbb242c988e843
ms.lasthandoff: 03/13/2017

---
# <a name="type-characters-visual-basic"></a>형식 문자(Visual Basic)
를 선언문의 데이터 형식을 지정 하는 것 외에도 일부 프로그래밍 요소와의 데이터 형식을 강제할 수는 *형식 문자*합니다. 형식 문자 어떠한 종류의 중간에 다른 문자 없이 요소를 다음에 나와야 합니다.  
  
 형식 문자 요소 이름의 일부가 아닙니다. 형식 문자 없이 문자 형식으로 정의 된 요소를 참조할 수 있습니다.  
  
## <a name="identifier-type-characters"></a>식별자 형식 문자  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]집합을 제공 *식별자 형식 문자*, 변수 또는 상수 데이터 형식을 지정 하는 선언에서 사용할 수 있는 합니다. 다음 표에서 사용할 수 있는 식별자 형식 문자 사용 예제를 보여 줍니다.  
  
|식별자 형식 문자|데이터 형식|예제|  
|-------------------------------|---------------|-------------|  
|`%`|`Integer`|`Dim L%`|  
|`&`|`Long`|`Dim M&`|  
|`@`|`Decimal`|`Const W@ = 37.5`|  
|`!`|`Single`|`Dim Q!`|  
|`#`|`Double`|`Dim X#`|  
|`$`|`String`|`Dim V$ = "Secret"`|  
  
 식별자 형식 문자가 없습니다는 `Boolean`, `Byte`, `Char`, `Date`, `Object`, `SByte`, `Short`, `UInteger`, `ULong`, 또는 `UShort` 데이터 형식 또는 배열 또는 구조체와 같은 복합 데이터 형식에 대 한 합니다.  
  
 일부 경우에 추가할 수 있습니다는 `$` 문자를 한 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 함수 예를 들어 `Left$` 대신 `Left`형식의 반환된 값을 얻기 위해 `String`합니다.  
  
 모든 경우에 식별자 형식 문자 다음에 나와야 식별자 이름.  
  
## <a name="literal-type-characters"></a>리터럴 형식 문자  
 A *리터럴* 데이터 형식의 특정 값의 텍스트 표현입니다.  
  
### <a name="default-literal-types"></a>기본 리터럴 형식  
 리터럴 형태가 일반적으로 코드에 표시 된 대로 해당 데이터 형식을 결정 합니다. 다음 표에서 이러한 기본 유형을 보여 줍니다.  
  
|리터럴 텍스트 형식|기본 데이터 형식|예제|  
|-----------------------------|-----------------------|-------------|  
|숫자, 더 소수 부분|`Integer`|`2147483647`|  
|너무 커서 숫자, 더 소수 부분`Integer`|`Long`|`2147483648`|  
|숫자, 소수 부분|`Double`|`1.2`|  
|큰따옴표로 묶인|`String`|`"A"`|  
|숫자 기호 사이 포함 된|`Date`|`#5/17/1993 9:32 AM#`|  
  
### <a name="forced-literal-types"></a>강제 리터럴 형식  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]집합을 제공 *리터럴 형식 문자*, 나타냅니다 강제로 형태로 아닌 데이터 형식을 취하도록 리터럴을 사용할 수 있습니다. 문자 리터럴의 끝에 추가 하 여이 작업을 수행 합니다. 다음 표에서 사용 예제를 사용할 수 있는 리터럴 형식 문자를 보여 줍니다.  
  
|리터럴 형식 문자|데이터 형식|예제|  
|----------------------------|---------------|-------------|  
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
  
 리터럴 형식 문자가 없습니다는 `Boolean`, `Byte`, `Date`, `Object`, `SByte`, 또는 `String` 데이터 형식 또는 배열 또는 구조체와 같은 복합 데이터 형식에 대 한 합니다.  
  
 리터럴 식별자 형식 문자를 사용할 수도 있습니다 (`%`, `&`, `@`, `!`, `#`, `$`), 변수, 상수 및 식입니다. 그러나 리터럴 형식 문자 (`S`, `I`, `L`, `D`, `F`, `R`, `C`) 리터럴에만 사용할 수 있습니다.  
  
 모든 경우, 리터럴 형식 문자 다음에 나와야 리터럴 값입니다.  
  
## <a name="hexadecimal-and-octal-literals"></a>8 진수 및&16; 진 리터럴  
 컴파일러는 일반적으로 10 진수 (밑수 10) 번호 시스템에는 정수 리터럴로 construes 합니다. 정수 리터럴을와 16 진수 (기 수 16)는 `&H` 접두사 및 있습니다 8 진수 (기 수 8) 사용 되도록 강제할 수는 `&O` 접두사입니다. 접두사 뒤의 숫자는 체계에 적합 해야 합니다. 다음 표에서이 보여 줍니다.  
  
|기 수|접두사|유효한 숫자 값|예제|  
|-----------------|------------|------------------------|-------------|  
|16진수|`&H`|0-9 및 A-F|`&HFFFF`|  
|8진수|`&O`|0-7|`&O77`|  
  
 리터럴 형식 문자 접두사가 붙은 리터럴을 따를 수 있습니다. 다음 예제에서는이 보여 줍니다.  
  
```  
Dim counter As Short = &H8000S  
Dim flags As UShort = &H8000US  
```  
  
 앞의 예제에서 `counter` -32768&10; 진수 값 및 `flags`&10; 진수 값 +&32768;을 갖습니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [기본 데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [데이터 형식 문제 해결](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)
