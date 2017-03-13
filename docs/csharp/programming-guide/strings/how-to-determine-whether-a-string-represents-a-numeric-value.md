---
title: "방법: 문자열이 숫자 값을 나타내는지 확인(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "숫자 문자열[C#]"
  - "문자열[C#], 숫자"
  - "숫자 입력 유효성 검사[C#]"
ms.assetid: a4e84e10-ea0a-489f-a868-503dded9d85f
caps.latest.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 9
---
# 방법: 문자열이 숫자 값을 나타내는지 확인(C# 프로그래밍 가이드)
문자열이 지정한 숫자 형식의 유효한 표현인지 확인하려면 모든 기본 숫자 형식에서 구현되며 <xref:System.DateTime> 및 <xref:System.Net.IPAddress> 같은 형식에서도 구현되는 정적 `TryParse` 메서드를 사용합니다.  다음 예제에서는 "108"이 유효한 [int](../../../csharp/language-reference/keywords/int.md)인지 확인하는 방법을 보여 줍니다.  
  
```  
int i = 0;   
string s = "108";  
bool result = int.TryParse(s, out i); //i now = 108  
```  
  
 문자열에 비숫자 문자가 포함되어 있는 경우 또는 숫자 값이 지정한 특정 형식에 비해 너무 크거나 너무 작은 경우 `TryParse`는 false를 반환하고 out 매개 변수를 0으로 설정합니다.  그렇지 않으면 true를 반환하고 out 매개 변수를 문자열의 숫자 값으로 설정합니다.  
  
> [!NOTE]
>  문자열은 숫자만 포함할 수 있으며 사용할 `TryParse` 메서드 형식에 아직 유효하지 않을 수 있습니다.  예를 들어 "256"은 `byte`에 대해서는 유효한 값이 아니지만 `int`에 대해서는 유효한 값입니다. 이때   98.6"은 `int`에 대해 유효한 값이 아니지만 `decimal`에 대해서는 유효한 값입니다.  
  
## 예제  
 다음 예제에서는 `long`, `byte` 및 `decimal` 값의 문자열 표현을 사용하여 `TryParse`를 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideStrings#14](../../../csharp/programming-guide/strings/codesnippet/CSharp/how-to-determine-whether-a-string-represents-a-numeric-value_1.cs)]  
  
## 강력한 프로그래밍  
 또한 기본 숫자 형식에서는 문자열이 유효한 숫자가 아닌 경우 예외를 throw하는 정적 메서드 `Parse`를 구현합니다.  숫자가 유효하지 않은 경우 false를 반환하기 때문에 일반적으로 `TryParse`를 사용하는 것이 더 효과적입니다.  
  
## .NET Framework 보안  
 `TryParse` 또는 `Parse`를 사용하여 텍스트 상자와 콤보 상자 등의 컨트롤로부터 항상 사용자 입력의 유효성을 검사합니다.  
  
## 참고 항목  
 [방법: 바이트 배열을 정수로 변환](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)   
 [방법: 문자열을 숫자로 변환](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)   
 [방법: 16진수 문자열과 숫자 형식 간 변환](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)   
 [숫자 문자열 구문 분석](../Topic/Parsing%20Numeric%20Strings%20in%20the%20.NET%20Framework.md)   
 [형식 서식 지정](../Topic/Formatting%20Types%20in%20the%20.NET%20Framework.md)