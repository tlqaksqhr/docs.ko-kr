---
title: "&gt; 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "> 연산자[C#]"
  - "보다 큼 연산자(>)[C#]"
ms.assetid: 26d3cb69-9c0b-4cc5-858b-5be1abd6659d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# &gt; 연산자(C# 참조)
모든 숫자 형식 및 열거형은 "보다 큼" 관계형 연산자\(`>`\)를 정의합니다. 이 연산자는 첫째 피연산자가 둘째 피연산자보다 크면 `true`를 반환하고 그렇지 않으면 `false`를 반환합니다.  
  
## 설명  
 사용자 정의 형식으로 `>` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  `>` 연산자를 오버로드할 경우에는 [\<](../../../csharp/language-reference/operators/less-than-operator.md) 연산자도 오버로드해야 합니다.  이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#29](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-operator_1.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [explicit](../../../csharp/language-reference/keywords/explicit.md)