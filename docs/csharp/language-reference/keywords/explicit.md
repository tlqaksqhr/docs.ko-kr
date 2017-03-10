---
title: "explicit(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "explicit_CSharpKeyword"
  - "explicit"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "explicit 키워드[C#]"
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# explicit(C# 참조)
`explicit` 키워드는 캐스트를 통해 호출해야 할 사용자 정의 형식 변환 연산자를 선언합니다.  예를 들어, 다음 연산자는 Fahrenheit라는 클래스를 Celsius라는 클래스로 변환합니다.  
  
 [!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_1.cs)]  
  
 이 변환 연산자는 다음과 같이 호출할 수 있습니다.  
  
 [!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_2.cs)]  
  
 변환 연산자는 소스 형식을 대상 형식으로 변환합니다.  소스 형식에서 변환 연산자를 제공합니다.  암시적 변환과 달리 명시적 변환은 캐스트를 통해 호출해야 합니다.  변환 연산으로 예외가 발생하거나 정보가 손실될 수 있는 경우 변환 연산을 `explicit`로 표시해야 합니다.  이렇게 해야 컴파일러가 예상치 않은 순서로 변환 연산을 호출하지 않습니다.  
  
 캐스트를 생략하면 컴파일 타임 오류 CS0266이 발생합니다.  
  
 자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Fahrenheit` 및 `Celsius` 클래스를 제공합니다. 각 클래스는 다른 클래스에 대한 명시적 변환 연산자를 제공합니다.  
  
 [!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_3.cs)]  
  
## 예제  
 아래 예제에서는 단일 10 진수를 나타내는 `Digit` 구조체를 정의합니다.  `byte`를 `Digit`로 변환하는 연산자가 정의되어 있지만 모든 바이트를 `Digit`로 변환할 수 있는 것은 아니므로 이 변환은 명시적입니다.  
  
 [!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/csharp/explicit_4.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [implicit](../../../csharp/language-reference/keywords/implicit.md)   
 [operator](../../../csharp/language-reference/keywords/operator.md)   
 [방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)   
 [명시적 변환을 사용자 정의 C\#에 연결 된](http://go.microsoft.com/fwlink/?LinkId=112384)