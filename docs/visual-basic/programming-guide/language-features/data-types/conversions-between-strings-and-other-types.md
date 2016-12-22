---
title: "Conversions Between Strings and Other Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "data type conversion, string"
  - "conversions, type"
  - "string conversion"
  - "conversions, data type"
  - "type conversion, string"
  - "regional options"
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Conversions Between Strings and Other Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

숫자, `Boolean` 또는 날짜\/시간 값을 `String`으로 변환할 수 있습니다.  반대로 문자열의 내용이 대상 데이터 형식의 유효한 값으로 해석될 수 있는 경우 문자열 값을 숫자, `Boolean` 또는 `Date`로 변환할 수도 있습니다.  변환할 수 없는 경우에는 런타임 오류가 발생합니다.  
  
 어느 방향이든 이러한 모든 할당에 대한 변환은 축소 변환입니다.  따라서 형식 변환 키워드\(`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort` 및 `CType`\)를 사용해야 합니다.  <xref:Microsoft.VisualBasic.Strings.Format%2A> 함수와 <xref:Microsoft.VisualBasic.Conversion.Val%2A> 함수는 문자열과 숫자 사이의 변환을 제어할 수 있는 추가 기능을 제공합니다.  
  
 클래스나 구조체를 정의한 경우 `String`과 해당 클래스 또는 구조체 형식 간의 형식 변환 연산자를 정의할 수 있습니다.  자세한 내용은 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조하십시오.  
  
## 숫자를 문자열로 변환  
 `Format` 함수를 사용하여 숫자를 서식이 지정된 문자열로 변환할 수 있습니다. 서식이 지정된 문자열에는 적절한 숫자뿐 아니라 통화 기호\(예: `$`\), 1000 단위 구분 기호 또는 *자릿수 구분 기호*\(예: `,`\), 소수 구분 기호\(예: `.`\) 등의 서식 기호도 포함될 수 있습니다.  `Format`에서는 Windows **제어판**에 지정된 **국가별 옵션** 설정에 따라 적절한 기호를 자동으로 사용합니다.  
  
 연결\(`&`\) 연산자는 다음 예제처럼 암시적으로 숫자를 문자열로 변환할 수 있다는 점에 유의하십시오.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## 문자열을 숫자로 변환  
 `Val` 함수를 사용하여 문자열의 숫자를 명시적으로 숫자로 변환할 수 있습니다.  `Val`은 숫자, 공백, 탭, 줄 바꿈 또는 마침표 이외의 문자가 있는 곳까지 문자열을 읽습니다.  "&O" 및 "&H" 시퀀스는 숫자 시스템의 기수를 변경하고 스캐닝을 종료합니다.  `Val`은 읽기를 중단할 때까지 모든 해당 문자를 숫자 값으로 변환합니다.  예를 들어, 다음 문은 값 `141.825`를 반환합니다.  
  
 `Val("   14   1.825 miles")`  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 문자열을 숫자 값으로 변환할 때 Windows **제어판**에 지정된 **국가별 옵션** 설정을 사용하여 1000 단위 구분 기호, 소수 구분 기호 및 통화 기호를 해석합니다.  이것은 한 설정에서 변환에 성공해도 다른 설정에서는 실패할 수 있다는 것을 의미합니다.  예를 들어, `"$14.20"`은 영어\(미국\) 로캘에서는 허용되지만 프랑스어 로캘에서는 허용되지 않습니다.  
  
## 참고 항목  
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [.NET Framework 기반의 국가별 응용 프로그램 소개](/visual-studio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)