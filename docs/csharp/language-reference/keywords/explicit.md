---
title: "explicit(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords: explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2661f46d79b13808bfb169bfbfffc1a17b866b2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="explicit-c-reference"></a>explicit(C# 참조)
`explicit` 키워드는 캐스트를 통해 호출해야 하는 사용자 정의 형식 변환 연산자를 선언합니다. 예를 들어 이 연산자는 Fahrenheit라는 클래스를 Celsius라는 클래스로 변환합니다.  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 이 변환 연산자는 다음과 같이 호출할 수 있습니다.  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 변환 연산자는 소스 형식을 대상 형식으로 변환합니다. 소스 형식은 변환 연산자를 제공합니다. 암시적 변환과 달리 명시적 변환 연산자는 캐스트를 통해 호출해야 합니다. 변환 연산으로 인해 예외가 발생하거나 정보가 손실될 경우 `explicit`로 표시해야 합니다. 이렇게 하면 컴파일러가 결과를 예측할 수 없는 변환 연산을 자동으로 호출하는 것을 방지할 수 있습니다.  
  
 캐스트를 생략하면 컴파일 시간 오류 CS0266이 발생합니다.  
  
 자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Fahrenheit` 및 `Celsius` 클래스를 제공하며, 각 클래스는 다른 클래스에 명시적 변환 연산자를 제공합니다.  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 자리 숫자를 나타내는 `Digit` 구조체를 정의합니다. `byte`에서 `Digit`로 변환하는 연산자를 정의하지만 일부 바이트는 `Digit`로 변환할 수 없기 때문에 명시적 변환이 됩니다.  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [implicit](../../../csharp/language-reference/keywords/implicit.md)  
 [연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)  
 [방법: 구조체 간의 사용자 정의 변환 구현](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 [Chained user-defined explicit conversions in C#](http://go.microsoft.com/fwlink/?LinkId=112384)(C#의 연결된 사용자 정의 명시적 변환)
