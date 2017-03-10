---
title: "|= 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "|=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|= 연산자(OR 할당)[C#]"
  - "OR 할당 연산자(|=)[C#]"
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# |= 연산자(C# 참조)
논리 OR 할당 연산자입니다.  
  
## 설명  
 다음과 같이 `|=` 할당 연산자를 사용하는 식은  
  
```  
x |= y  
```  
  
 동일한 함수는  
  
```  
x = x | y  
```  
  
 그러나 `x`가 한 번만 계산된다는 점은 다릅니다.  [&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)는 정수 계열 피연산자에 대해서는 비트 논리 OR 연산을 수행하고, bool 피연산자에 대해서는 논리 OR를 수행합니다.  
  
 `|=` 연산자는 직접 오버로드될 수 없지만 사용자 정의 형식으로 [&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  
  
## 예제  
 [!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#10)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)