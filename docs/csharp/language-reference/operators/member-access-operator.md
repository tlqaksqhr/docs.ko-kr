---
title: ". 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "._CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ". 연산자[C#]"
  - "점(.) 연산자 [C#]"
  - "멤버 액세스 연산자(.) [C#]"
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# . 연산자(C# 참조)
도트 연산자\(`.`\)는 멤버 액세스에 사용됩니다.  도트 연산자는 형식 또는 네임스페이스의 멤버를 지정합니다.  예를 들어, 도트 연산자는 .NET Framework 클래스 라이브러리 내의 특정 메서드에 액세스하는 데 사용됩니다.  
  
 [!code-cs[csRefOperators#16](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#16)]  
  
 예를 들어, 다음 클래스를 확인해 보십시오.  
  
 [!code-cs[csRefOperators#17](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#17)]  
  
 [!code-cs[csRefOperators#18](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#18)]  
  
 변수 `s`에는 `a` 및 `b`의 두 멤버가 있습니다. 이들 멤버에 액세스하기 위해 다음과 같이 도트 연산자를 사용합니다.  
  
 [!code-cs[csRefOperators#19](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#19)]  
  
 또한 해당 멤버가 속한 네임스페이스나 인터페이스 등을 지정하는 정규화된 이름을 형성하기 위해서도 도트 연산자를 사용합니다.  
  
 [!code-cs[csRefOperators#20](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#20)]  
  
 다음과 같이 using 지시문을 사용하면 일부 이름 한정이 선택적인 요소가 됩니다.  
  
 [!code-cs[csRefOperators#21](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#21)]  
  
 하지만 다음과 같이 식별자가 모호할 경우에는 한정이 필요합니다.  
  
 [!code-cs[csRefOperators#22](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#22)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)