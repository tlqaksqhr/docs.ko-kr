---
title: "^= 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "^=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "^= 연산자[C#]"
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# ^= 연산자(C# 참조)
배타적 OR 할당 연산자입니다.  
  
## 설명  
 다음 형식의 식은  
  
```  
x ^= y  
```  
  
 다음과 같이 계산되며  
  
```  
x = x ^ y  
```  
  
 그러나 `x`가 한 번만 계산된다는 점은 다릅니다.  [^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)는 정수 계열 피연산자에 대해서는 비트 배타적 OR 연산을 수행하고, [bool](../../../csharp/language-reference/keywords/bool.md) 피연산자에 대해서는 논리 배타적 논리 OR 연산을 수행합니다.  
  
 ^\= 연산자는 직접 오버로드될 수 없지만 사용자 정의 형식으로 [^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  
  
## 예제  
 [!code-cs[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)