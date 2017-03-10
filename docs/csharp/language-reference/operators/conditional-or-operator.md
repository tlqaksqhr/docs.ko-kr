---
title: "|| 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "||_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "|| 연산자[C#]"
  - "조건부 OR 연산자(||)[C#]"
  - "논리합 연산자[C#]"
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
caps.latest.revision: 25
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 25
---
# || 연산자(C# 참조)
조건부 논리합 연산자 \(`||`\)는 논리 OR를 수행 그 `bool` 피연산자입니다.  첫 번째 피연산자가 계산 되는 경우 `true`, 두번째 피연산자는 평가 되지 않습니다.  첫 번째 피연산자가 계산 되는 경우 `false`를 두 번째 연산자 OR 식을 전체적으로 계산 되는지 여부를 결정 `true` 또는 `false`.  
  
## 설명  
 아래 연산은  
  
```  
x || y  
```  
  
 다음 연산에 해당하지만  
  
```  
x | y  
```  
  
 경우를 제외 하 고 `x` 는 `true`, `y` OR 연산 이므로 계산 하지 `true` 의 값에 관계 없이 `y`.  이 개념은 단락"계산"으로 알려져 있습니다.  
  
 오버 OR 연산자를 제외한 정규 논리 연산자의 오버 로드할 수 없습니다 및  [true](../../../csharp/language-reference/keywords/true.md) 및  [false](../../../csharp/language-reference/keywords/false.md) 연산자, 특정 제한으로도 간주 조건부 논리 연산자의 오버 로드 됩니다.  
  
## 예제  
 다음 예제에서는 표현식을 사용 하 `||` 에서 첫째 피연산자만 계산 합니다.  사용 하는 식 `|`두 피연산자를 모두 계산합니다.  두 번째 예제에서는 두 피연산자를 모두 계산 하는 경우 런타임 예외를 발생 합니다.  
  
 [!code-cs[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#52)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)