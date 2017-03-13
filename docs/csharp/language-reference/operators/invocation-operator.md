---
title: "() 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "()_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "() 연산자[C#]"
  - "캐스트 연산자[C#]"
  - "형식 변환[C#], () 연산자"
ms.assetid: 846e1f94-8a8c-42fc-a42c-fbd38e70d8cc
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# () 연산자(C# 참조)
괄호는 식에서 연산의 순서를 지정하기 위해 사용하는 용도 이외에 다음과 같은 작업을 수행하는 데도 사용합니다.  
  
1.  캐스팅 또는 형식 변환을 지정합니다.  
  
     [!code-cs[csRefOperators#1](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_1.cs)]  
  
2.  메서드 또는 대리자 호출.  
  
     [!code-cs[csRefOperators#2](../../../csharp/language-reference/operators/codesnippet/CSharp/invocation-operator_2.cs)]  
  
## 설명  
 캐스트는 한 형식에서 다른 형식으로의 변환 연산자를 명시적으로 호출합니다. 따라서 해당하는 변환 연산자가 정의되어 있지 않으면 캐스팅할 수 없습니다.  변환 연산자 정의에 대해서는 [explicit](../../../csharp/language-reference/keywords/explicit.md) 및 [implicit](../../../csharp/language-reference/keywords/implicit.md)를 참조하십시오.  
  
 `()` 연산자는 오버로드되지 않습니다.  
  
 자세한 내용은 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)를 참조하십시오.  
  
 캐스트 식을 사용하면 구문이 모호해질 수 있습니다.  예를 들어 `(x)–y`라는 식은 \-y를 x 형식으로 캐스팅하는 캐스트 식으로 해석될 수도 있고, 괄호로 둘러싼 식과 결합되어 x \- y 값을 계산하는 가감 식으로 해석될 수도 있습니다.  
  
 메서드 호출에 대한 자세한 내용은 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)를 참조하십시오.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)