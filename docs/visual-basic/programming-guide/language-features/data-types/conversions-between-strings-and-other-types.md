---
title: "문자열과 다른 형식 (Visual Basic) 간의 변환 | Microsoft 문서"
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
- data type conversion, string
- conversions, type
- string conversion
- conversions, data type
- type conversion, string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
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
ms.openlocfilehash: 2d0a5fc7327ecd6339b5021e1b4cb87cc54bd2bc
ms.lasthandoff: 03/13/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a>문자열과 다른 형식 사이의 변환(Visual Basic)
숫자를 변환할 수 `Boolean`, 또는 날짜/시간 값을 한 `String`합니다. 반대 방향으로 변환할 수 있습니다-숫자, 문자열 값에서 `Boolean`, 또는 `Date` -문자열의 내용을 대상 데이터 형식의 유효한 값으로 해석 될 수 있습니다. 그렇지 않을 경우 런타임 오류가 발생 합니다.  
  
 어느 방향으로 이러한 모든 할당에 대 한 변환은 축소 변환 합니다. You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`). <xref:Microsoft.VisualBasic.Strings.Format%2A>및 <xref:Microsoft.VisualBasic.Conversion.Val%2A>함수 문자열 및 숫자 간의 변환에 대 한 추가 제어를 제공 합니다.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A>  
  
 간의 형식 변환 연산자를 정의할 수 있는 클래스 또는 구조체를 정의 하는 경우 `String` 및 클래스 또는 구조체의 형식입니다. 자세한 내용은 참조 [하는 방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.  
  
## <a name="conversion-of-numbers-to-strings"></a>숫자를 문자열로 변환  
 사용할 수 있습니다는 `Format` 뿐만 아니라 적절 한 숫자를 포함할 수 있는 서식이 지정된 된 문자열에 숫자를 변환할 작동 하지만 통화 기호 등의 기호 서식 지정 (같은 `$`), 수천 구분 기호 또는 *숫자 구분 기호* (와 같은 `,`), 및 소수 구분 기호 (같은 `.`). `Format`에 따라 적절 한 기호를 자동으로 사용 하 여 **국가별 옵션** Windows에 지정 된 설정을 **제어판**합니다.  
  
 연결 (`&`) 연산자는 다음 예제와 같이 암시적으로 숫자를 문자열로 변환할 수 있습니다.  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a>문자열을 숫자로 변환  
 사용할 수는 `Val` 함수를 명시적으로 문자열의 자릿수를 숫자로 변환 합니다. `Val`숫자, 공백, 탭, 줄 바꿈 또는 기간 이외의 문자를 만날 때까지 문자열을 읽습니다. 시퀀스를 "< / O"와 "< / H" 번호 시스템의 기본을 변경 하 고 검색을 종료 합니다. 읽기를 중단할 때까지 `Val` 모든 해당 문자는 숫자 값으로 변환 합니다. 다음 문은 값을 반환 하는 예를 들어 `141.825`합니다.  
  
 `Val("   14   1.825 miles")`  
  
 때 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변환 문자열을 숫자 값을 사용 하 여는 **국가별 옵션** Windows에 지정 된 설정을 **제어판**&1000; 단위를 해석 하 구분 기호, 소수 구분 기호 및 통화 기호입니다. 즉, 변환을 설정 해도 다른 하나에 성공할 수도 있습니다. 예를 들어 `"$14.20"` 허용 되는 프랑스어 로캘이 있지만 영어 (미국) 로캘을에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 형식 변환](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [암시적 변환과 명시적 변환](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [방법: Visual Basic에서 다른 형식으로 변환](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)   
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [.NET Framework 기반의 국가별 응용 프로그램 소개](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
