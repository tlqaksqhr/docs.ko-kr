---
title: '방법: 16진수 문자열과 숫자 형식 간 변환(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- hexadecimal strings [C#], converting to numeric type
- conversions [C#], hexidecimal strings
- strings [C#], converting hexadecimal strings
- hexadecimal strings [C#]
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
ms.openlocfilehash: 1a5bde0a9169a78e179a69c7a2f4080e5a465f54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33334703"
---
# <a name="how-to-convert-between-hexadecimal-strings-and-numeric-types-c-programming-guide"></a>방법: 16진수 문자열과 숫자 형식 간 변환(C# 프로그래밍 가이드)
이 예제에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
-   [string](../../../csharp/language-reference/keywords/string.md)에 있는 각 문자의 16진수 값을 가져옵니다.  
  
-   16진수 문자열의 각 값에 해당하는 [char](../../../csharp/language-reference/keywords/char.md)을 가져옵니다.  
  
-   16진수 `string`을 [int](../../../csharp/language-reference/keywords/int.md)로 변환합니다.  
  
-   16진수 `string`을 [float](../../../csharp/language-reference/keywords/float.md)로 변환합니다.  
  
-   [byte](../../../csharp/language-reference/keywords/byte.md) 배열을 16진수 `string`으로 변환합니다.  
  
## <a name="example"></a>예  
 이 예제에서는 `string`에 있는 각 문자의 16진수 값을 출력합니다. 먼저 `string`을 문자 배열로 구문 분석합니다. 그런 다음 각 문자에서 <xref:System.Convert.ToInt32%28System.Char%29>를 호출하여 해당 숫자 값을 가져옵니다. 마지막으로, `string`에서 숫자의 형식을 16진수 표현으로 지정합니다.  
  
 [!code-csharp[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_1.cs)]  
  
## <a name="example"></a>예  
 이 예제에서는 16진수 값의 `string`을 구문 분석하고 각 16진수 값에 해당하는 문자를 출력합니다. 먼저 [Split(Char\[\])](xref:System.String.Split(System.Char[])) 메서드를 호출하여 각 16진수 값을 배열의 개별 `string`으로 가져옵니다. 그런 다음 <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>를 호출하여 16진수 값을 [int](../../../csharp/language-reference/keywords/int.md)로 표현된 10진수 값으로 변환합니다. 문자 코드에 해당하는 문자를 가져오는 두 가지 방법을 보여 줍니다. 첫 번째 방법은 정수 인수에 해당하는 문자를 `string`으로 반환하는 <xref:System.Char.ConvertFromUtf32%28System.Int32%29>를 사용합니다. 두 번째 방법은 `int`를 [char](../../../csharp/language-reference/keywords/char.md)로 명시적으로 캐스팅합니다.  
  
 [!code-csharp[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_2.cs)]  
  
## <a name="example"></a>예  
 이 예제에서는 <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> 메서드를 호출하여 16진수 `string`을 정수로 변환하는 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_3.cs)]  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.BitConverter?displayProperty=nameWithType> 클래스 및 <xref:System.Int32.Parse%2A?displayProperty=nameWithType> 메서드를 사용하여 16진수 `string`을 [float](../../../csharp/language-reference/keywords/float.md)로 변환하는 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_4.cs)]  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:System.BitConverter?displayProperty=nameWithType> 클래스를 사용하여 [byte](../../../csharp/language-reference/keywords/byte.md) 배열을 16진수 문자열로 변환하는 방법을 보여 줍니다.  
  
 [!code-csharp[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-between-hexadecimal-strings-and-numeric-types_5.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [표준 숫자 형식 문자열](../../../standard/base-types/standard-numeric-format-strings.md)  
 [유형](../../../csharp/programming-guide/types/index.md)  
 [방법: 문자열이 숫자 값을 나타내는지 확인](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)
