---
title: "연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "[]_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "첨자 연산자[C#]"
  - "대괄호 [ ] 연산자[C#]"
  - "[] 연산자[C#]"
  - "인덱싱 연산자[C#]"
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# 연산자(C# 참조)
대괄호\(`[]`\)는 배열, 인덱서 및 특성에 사용합니다.  또한 포인터에도 사용합니다.  
  
## 설명  
 다음 예에서 볼 수 있는 것처럼 배열 형식은 `[]` 앞에 있는 형식입니다.  
  
 [!code-cs[csRefOperators#43](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#43)]  
  
 다음 예에서 볼 수 있는 것처럼 배열 요소에 액세스하려면 원하는 요소의 인덱스를 대괄호로 묶습니다.  
  
 [!code-cs[csRefOperators#44](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#44)]  
  
 배열 인덱스가 범위를 벗어나면 예외가 throw됩니다.  
  
 배열 인덱싱 연산자는 오버로드할 수 없지만 형식을 사용하면 하나 이상의 매개 변수를 가지는 인덱서와 속성을 정의할 수 있습니다.  인덱서 매개 변수는 배열 인덱스처럼 대괄호로 묶지만 배열 인덱스가 정수 계열이어야 하는 것과 달리 인덱서 매개 변수는 형식에 관계없이 선언할 수 있습니다.  
  
 예를 들어, .NET Framework에서는 임의 형식의 키와 값을 연결하는 `Hashtable` 형식을 정의합니다.  
  
 [!code-cs[csRefOperators#45](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#45)]  
  
 또한 대괄호는 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)을 지정하기 위해서도 사용합니다.  
  
 [!code-cs[csRefOperators#46](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#46)]  
  
 대괄호를 포인터의 인덱스 참조에 사용할 수 있습니다.  
  
 [!code-cs[csRefOperators#47](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#47)]  
  
 범위 검사는 수행하지 않습니다.  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [인덱서](../../../csharp/programming-guide/indexers/index.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)