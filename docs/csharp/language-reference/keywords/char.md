---
title: "char(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "char"
  - "char_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "char 데이터 형식[C#]"
ms.assetid: b51cf4fb-124c-4067-af48-afbac122b228
caps.latest.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 27
---
# char(C# 참조)
`char` 키워드의 인스턴스를 선언 하는 데 사용 된 <xref:System.Char?displayProperty=fullName> 구조체는.NET Framework 사용 하 여 유니코드 문자를 나타냅니다.  값은 `Char` 개체는 16 비트 숫자 \(서 수\) 값입니다.  
  
 유니코드 문자는 대부분의 전세계 언어를 나타내는 데 사용 됩니다.  
  
|형식|범위|크기|.NET Framework 형식|  
|--------|--------|--------|-----------------------|  
|`char`|U \+ 0000 ~ U \+ FFFF|유니코드 16비트 문자|<xref:System.Char?displayProperty=fullName>|  
  
## 리터럴  
 `char` 형식의 상수는 문자 리터럴, 16진수 이스케이프 시퀀스 또는 유니코드 표현으로 작성할 수 있습니다.  또한 정수 계열 문자 코드를 변환할 수 있습니다.  다음 예제에서는 `char` 변수 네 개를 동일한 문자 `X`로 초기화합니다.  
  
 [!code-cs[csrefKeywordsTypes#19](../../../csharp/language-reference/keywords/codesnippet/csharp/char_1.cs)]  
  
## 변환  
 `char` 형식은 [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md) 또는 [decimal](../../../csharp/language-reference/keywords/decimal.md)로 암시적으로 변환할 수 있습니다.  그러나 다른 형식에서 `char` 형식으로의 암시적 변환은 없습니다.  
  
 <xref:System.Char?displayProperty=fullName> 형식은 `char` 값 처리에 사용할 수 있는 몇 가지 정적 메서드를 제공합니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 <xref:System.Char>   
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [정수 계열 형식 표](../../../csharp/language-reference/keywords/integral-types-table.md)   
 [기본 제공 형식 표](../../../csharp/language-reference/keywords/built-in-types-table.md)   
 [암시적 숫자 변환 표](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)   
 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)   
 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)   
 [문자열](../../../csharp/programming-guide/strings/index.md)