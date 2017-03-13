---
title: "&amp; 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "비트 AND 연산자[C#]"
  - "앰퍼샌드 연산자(&)[C#]"
  - "& 연산자[C#]"
  - "AND 연산자(&)[C#]"
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
caps.latest.revision: 19
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 19
---
# &amp; 연산자(C# 참조)
& 연산자는 단항 연산자로 사용하거나 이항 연산자로 사용할 수 있습니다.  
  
## 설명  
 단항 & 연산자는 피연산자의 주소를 반환합니다\([unsafe](../../../csharp/language-reference/keywords/unsafe.md) 컨텍스트 필요\).  
  
 이항 & 연산자는 정수 계열 형식과 `bool`에 대해 미리 정의되어 있습니다.  정수 계열 형식의 경우 & 연산자는 피연산자의 비트 논리 AND를 계산합니다.  `bool` 피연산자의 경우 & 연산자는 피연산자에 대한 논리 AND를 계산합니다. 즉, 두 피연산자가 모두 `true`인 경우에만 결과가 `true`입니다.  
  
 `&` 연산자는 첫째 피연산자의 값에 상관없이 두 연산자를 모두 계산합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csRefOperators#37](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_1.cs)]  
  
 사용자 정의 형식으로 이항 `&` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#38](../../../csharp/language-reference/operators/codesnippet/CSharp/and-operator_2.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)