---
title: "&gt;&gt;= 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">>=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">>= 연산자(오른쪽 시프트 할당)[C#]"
  - "오른쪽 시프트 할당 연산자(>>=)[C#]"
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# &gt;&gt;= 연산자(C# 참조)
오른쪽 시프트 할당 연산자입니다.  
  
## 설명  
 다음 형식의 식은  
  
```  
x >>= y  
```  
  
 다음과 같이 계산되며  
  
```  
x = x >> y  
```  
  
 그러나 `x`가 한 번만 계산된다는 점은 다릅니다.  [\>\> 연산자](../../../csharp/language-reference/operators/right-shift-operator.md)는 `y` 값으로 지정한 비트 수만큼 `x`를 비트 단위로 오른쪽으로 이동합니다.  
  
 \>\>\= 연산자는 직접 오버로드될 수 없지만 사용자 정의 형식으로 [\>\> 연산자](../../../csharp/language-reference/operators/right-shift-operator.md)를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  
  
## 예제  
 [!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#11)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)