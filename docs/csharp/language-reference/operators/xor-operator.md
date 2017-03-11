---
title: "^ 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "^_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^ 연산자[C#]"
  - "비트 배타적 OR 연산자[C#]"
ms.assetid: b09bc815-570f-4db6-a637-5b4ed99d014a
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# ^ 연산자(C# 참조)
이항 `^` 연산자는 정수 계열 형식과 `bool`에 대해 미리 정의되어 있습니다.  정수 계열 형식의 경우 `^` 연산자는 피연산자의 비트 배타적 OR를 계산합니다.  `bool` 피연산자의 경우 `^` 연산자는 피연산자의 논리 배타적 논리 OR을 계산합니다. 즉, 두 피연산자 중 하나가 `true`인 경우에만 결과가 `true`입니다.  
  
## 설명  
 사용자 정의 형식으로 `^` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#30](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#30)]  
  
 이전 예제의 `0xf8 ^ 0x3f` 계산은 각각 16진수 값 F8과 3F에 해당하는 다음 두 이진 값의 비트 배타적 논리합\(Exclusive\-OR\)을 수행합니다.  
  
 `1111 1000`  
  
 `0011 1111`  
  
 배타적 논리합\(Exclusive\-OR\)의 결과는 `1100 0111`이며, 16진수의 C7에 해당합니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)