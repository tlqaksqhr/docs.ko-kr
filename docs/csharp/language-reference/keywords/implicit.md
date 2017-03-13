---
title: "implicit(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "implicit"
  - "implicit_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "implicit 키워드[C#]"
ms.assetid: 34db590e-eb3a-4f11-88d0-ffb3cd753dab
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# implicit(C# 참조)
`implicit` 키워드는 암시적인 사용자 정의 형식 변환 연산자를 선언하는 데 사용됩니다.  이 키워드를 사용하면 사용자 정의 형식과 다른 형식 간의 암시적 변환이 가능합니다. 단, 변환으로 인해 데이터가 손실되지 않는 경우에 한합니다.  
  
## 예제  
 [!code-cs[csrefKeywordsConversion#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicit_1.cs)]  
  
 암시적 변환은 불필요한 캐스트를 제거하여 소스 코드를 읽기 쉽도록 합니다.  그러나 암시적 변환을 수행할 때는 프로그래머가 한 형식을 다른 형식으로 명시적으로 캐스팅할 필요가 없으므로 예기치 않은 결과가 발생하지 않도록 주의해야 합니다.  일반적으로 프로그래머가 개입하지 않고 암시적 변환 연산자를 안전하게 사용하려면 해당 연산자에서 예외를 throw하거나 정보가 손실되지 않도록 해야 합니다.  변환 연산자가 이러한 기준을 충족시키지 못하는 경우 해당 연산자를 `explicit`로 표시해야 합니다.  자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)   
 [operator](../../../csharp/language-reference/keywords/operator.md)   
 [방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)