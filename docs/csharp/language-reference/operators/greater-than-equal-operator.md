---
title: "&gt;= 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - ">=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - ">= 연산자[C#]"
  - "크거나 같음 연산자(>=)[C#]"
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# &gt;= 연산자(C# 참조)
모든 숫자 형식 및 열거형은 "크거나 같음" 관계형 연산자\(`>=`\)를 정의합니다. 이 연산자는 첫째 피연산자가 둘째 피연산자보다 크거나 같으면 `true`를 반환하고 그렇지 않으면 `false`를 반환합니다.  
  
## 설명  
 사용자 정의 형식으로 `>=` 연산자를 오버로드할 수 있습니다.  자세한 내용은 [연산자](../../../csharp/language-reference/keywords/operator.md)를 참조하십시오.  `>=` 연산자를 오버로드할 경우에는 [\<\=](../../../csharp/language-reference/operators/less-than-equal-operator.md) 연산자도 오버로드해야 합니다.  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#39)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)