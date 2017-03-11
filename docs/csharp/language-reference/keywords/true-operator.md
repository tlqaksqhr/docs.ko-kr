---
title: "true 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "true 연산자[C#]"
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# true 연산자(C# 참조)
피연산자가 true임을 나타낼 경우 [bool](../../../csharp/language-reference/keywords/bool.md) 값 `true`를 반환하고, 그렇지 않을 경우 `false`를 반환합니다.  
  
 C\# 2.0 이전 버전에서는 `true` 및 `false` 연산자를 사용해서 `SqlBool`과 같은 형식과 호환되는 사용자 정의 null 허용 값 형식을 만들었습니다.  그러나 이 버전에서는 null 허용 값 형식에 대한 지원이 기본적으로 제공되므로 가능하면 `true` 및 `false` 연산자를 오버로드하는 대신 null 허용 값 형식을 사용해야 합니다.  자세한 내용은 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)를 참조하십시오.  
  
 null 허용 부울을 사용하면 `a != b` 식은 두 값 중 하나 이상이 null일 수 있으므로 `!(a == b)`과 반드시 일치하지는 않습니다.  식의 null 값을 올바르게 식별하려면 `true` 및 `false` 연산자를 개별적으로 오버로드해야 합니다.  다음 예제에서는 `true` 및 `false` 연산자를 오버로드하여 사용하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/csharp/csrefKeywordsOperator/csrefKeywordsOperators.cs#16)]  
  
 `true` 및 `false` 연산자를 오버로드하는 형식은 [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) 및 [for](../../../csharp/language-reference/keywords/for.md) 문과 [조건식](../../../csharp/language-reference/operators/conditional-operator.md)에서 제어식에 사용할 수 있습니다.  
  
 `true` 연산자를 정의하는 형식은 [false](../../../csharp/language-reference/keywords/false.md) 연산자도 정의해야 합니다.  
  
 한 형식으로 조건부 논리 연산자\([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 및 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)\)를 직접 오버로드할 수 없지만, 일반적인 논리 연산자와 `true` 및 `false` 연산자를 오버로드하면 조건부 논리 연산자를 오버로드한 것과 같은 결과를 얻을 수 있습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [FALSE](../../../csharp/language-reference/keywords/false.md)