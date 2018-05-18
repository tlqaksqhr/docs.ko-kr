---
title: char(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- char
- char_CSharpKeyword
helpviewer_keywords:
- char data type [C#]
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
ms.openlocfilehash: 67efc4b9600d7d722ebbef83819e143506a93c26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="char-c-reference"></a>char(C# 참조)
`char` 키워드는 .NET Framework에서 유니코드 문자를 표현하는 데 사용하는 <xref:System.Char?displayProperty=nameWithType> 구조체의 인스턴스를 선언하는 데 사용됩니다. `Char` 개체의 값은 16비트 숫자(서수) 값입니다.  
  
 유니코드 문자는 전 세계에서 대부분의 문자 체계를 표현하는 데 사용됩니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|----------|-----------|----------|-------------------------|  
|`char`|U+0000~U+FFFF|유니코드 16비트 문자|<xref:System.Char?displayProperty=nameWithType>|  
  
## <a name="literals"></a>리터럴  
 `char` 형식의 상수는 문자 리터럴, 16진수 이스케이프 시퀀스 또는 유니코드 표현으로 기록될 수 있습니다. 정수 문자 코드를 캐스트할 수도 있습니다. 다음 예제에서 `char` 변수 4개는 동일 문자 `X`를 사용하여 초기화됩니다.  
  
 [!code-csharp[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/CSharp/char_1.cs)]  
  
## <a name="conversions"></a>변환  
 `char`는 [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 암시적으로 변환될 수 있습니다. 그러나 기타 형식에서 `char` 형식으로의 암시적 변환은 없습니다.  
  
 <xref:System.Char?displayProperty=nameWithType> 형식은 `char` 값 작업을 위한 몇 가지 정적 메서드를 제공합니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Char>  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)  
 [문자열](../../../csharp/programming-guide/strings/index.md)
