---
title: "방법: 16진수 문자열과 숫자 형식 간 변환(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "변환[C#], 16진수 문자열"
  - "16진수 문자열[C#]"
  - "16진수 문자열[C#], 숫자 형식으로 변환"
  - "문자열[C#], 16진수 문자열 변환"
ms.assetid: 7115c49f-7d1d-40c3-8bd9-aae0cc1d46b6
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# 방법: 16진수 문자열과 숫자 형식 간 변환(C# 프로그래밍 가이드)
이 예제에서는 다음과 같은 작업을 수행하는 방법을 보여 줍니다.  
  
-   [string](../../../csharp/language-reference/keywords/string.md)에서 각 문자의 16진수 값을 가져옵니다.  
  
-   16진수 문자열의 각 값에 해당하는 [char](../../../csharp/language-reference/keywords/char.md)을 가져옵니다.  
  
-   16진수 `string`을 [int](../../../csharp/language-reference/keywords/int.md)로 변환합니다.  
  
-   16진수 `string`을 [float](../../../csharp/language-reference/keywords/float.md)로 변환합니다.  
  
-   [byte](../../../csharp/language-reference/keywords/byte.md) 배열을 16진수 `string`으로 변환합니다.  
  
## 예제  
 이 예제에서는 `string`에 있는 각 문자의 16진수 값을 출력합니다.  먼저 `string`을 문자 배열로 구문 분석합니다.  그런 다음 각 문자에 대해 <xref:System.Convert.ToInt32%28System.Char%29>를 호출하여 해당 숫자 값을 가져옵니다.  마지막으로 이 숫자를 16진수 형식으로 `string`에 나타냅니다.  
  
 [!code-cs[csProgGuideTypes#30](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-between-h_1.cs)]  
  
## 예제  
 이 예제에서는 16진수 값의 `string`을 구문 분석하고 각 16진수 값에 해당하는 문자를 출력합니다.  먼저 [Split\(Char\<xref:System.String.Split%28System.Char%5B%5D%29> 메서드를 호출하여 각 16진수 값을 배열의 개별 `string`으로 가져옵니다.  그런 다음 <xref:System.Convert.ToInt32%28System.String%2CSystem.Int32%29>를 호출하여 16진수 값을 [int](../../../csharp/language-reference/keywords/int.md)로 표현되는 10진수로 변환합니다.  이 예제에서는 문자 코드에 해당하는 문자를 가져오는 두 가지 방법을 보여 줍니다.  첫 번째 방법에서는 정수 인수에 해당하는 문자를 `string`으로 반환하는 <xref:System.Char.ConvertFromUtf32%28System.Int32%29>를 사용합니다.  두 번째 방법에서는 `int`를 [char](../../../csharp/language-reference/keywords/char.md)로 명시적으로 캐스팅합니다.  
  
 [!code-cs[csProgGuideTypes#31](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-between-h_2.cs)]  
  
## 예제  
 이 예제에서는 <xref:System.Int32.Parse%28System.String%2CSystem.Globalization.NumberStyles%29> 메서드를 호출하여 16진수 `string`을 정수로 변환하는 다른 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#32](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-between-h_3.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.BitConverter?displayProperty=fullName> 클래스 및 <xref:System.Int32.Parse%2A?displayProperty=fullName> 메서드를 사용하여 16진수 `string`을 [float](../../../csharp/language-reference/keywords/float.md)로 변환하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#39](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-between-h_4.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.BitConverter?displayProperty=fullName> 클래스를 사용하여 [byte](../../../csharp/language-reference/keywords/byte.md) 배열을 16진수 문자열로 변환하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideTypes#38](../../../csharp/programming-guide/nullable-types/codesnippet/csharp/how-to-convert-between-h_5.cs)]  
  
## 참고 항목  
 [표준 숫자 형식 문자열](../Topic/Standard%20Numeric%20Format%20Strings.md)   
 [형식](../../../csharp/programming-guide/types/index.md)   
 [방법: 문자열이 숫자 값을 나타내는지 확인](../../../csharp/programming-guide/strings/how-to-determine-whether-a-string-represents-a-numeric-value.md)