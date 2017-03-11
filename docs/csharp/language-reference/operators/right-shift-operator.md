---
title: "&gt;&gt; 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">>_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">> 연산자[C#]"
  - "오른쪽 시프트 연산자(>>)[C#]"
ms.assetid: a07f8679-d318-4ef8-b38b-65903efb8056
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# &gt;&gt; 연산자(C# 참조)
오른쪽 시프트 연산자\(`>>`\)는 첫째 피연산자를 둘째 피연산자에서 지정한 비트 수만큼 비트 단위로 오른쪽으로 이동합니다.  
  
## 설명  
 첫째 피연산자가 32비트 용량의 [int](../../../csharp/language-reference/keywords/int.md) 또는 [uint](../../../csharp/language-reference/keywords/uint.md) 형식이면 시프트 횟수는 둘째 피연산자의 하위 5비트\(second operand & 0x1f\)로 지정됩니다.  
  
 첫째 연산자가 64비트 용량의 [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식이면 시프트 횟수는 둘째 피연산자의 하위 6비트\(second operand & 0x3f\)로 지정됩니다.  
  
 첫째 피연산자가 [int](../../../csharp/language-reference/keywords/int.md)또는 [long](../../../csharp/language-reference/keywords/long.md) 형식이면 오른쪽 시프트는 비어 있는 상위 비트가 부호 비트로 설정되는 산술 시프트입니다.  첫째 피연산자가 [uint](../../../csharp/language-reference/keywords/uint.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식이면 오른쪽 시프트는 상위 비트가 0으로 채워지는 논리 시프트입니다.  
  
 사용자 정의 형식으로 `>>` 연산자를 오버로드할 수 있습니다. 이 경우, 첫째 피연산자의 형식은 사용자 정의 형식이어야 하며 둘째 피연산자의 형식은 [int](../../../csharp/language-reference/keywords/int.md)여야 합니다.  자세한 내용은 [연산자](../../../csharp/language-reference/keywords/operator.md)를 참조하십시오.  이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#26](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#26)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)