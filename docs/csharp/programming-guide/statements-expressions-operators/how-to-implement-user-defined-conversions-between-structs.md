---
title: "방법: 구조체 간의 사용자 정의 변환 구현(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "사용자 정의 변환[C#]"
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# 방법: 구조체 간의 사용자 정의 변환 구현(C# 프로그래밍 가이드)
다음은 `RomanNumeral`과 `BinaryNumeral`의 두 구조체를 정의하고 이 두 구조체 간의 변환을 보여 주는 예제입니다.  
  
## 예제  
 [!code-cs[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## 강력한 프로그래밍  
  
-   앞의 예제에 있는 다음 문을 살펴 봅니다.  
  
     [!code-cs[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     이 문에서는 `RomanNumeral`을 `BinaryNumeral`로 변환합니다.  `RomanNumeral`에서 `BinaryNumeral`로 직접 변환되지 않으므로 캐스트를 사용하여 `RomanNumeral`에서 `int`로 변환하고 또 다른 캐스트를 사용하여 `int`에서 `BinaryNumeral`로 변환합니다.  
  
-   또한 다음 문을 살펴 봅니다.  
  
     [!code-cs[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     이 문에서는 `BinaryNumeral`을 `RomanNumeral`로 변환합니다.  `RomanNumeral`은 `BinaryNumeral`로부터의 암시적 변환을 정의하므로 캐스트가 필요하지 않습니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [변환 연산자](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)