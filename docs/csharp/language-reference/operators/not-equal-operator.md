---
title: "!= 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "!=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "!= 연산자[C#]"
  - "같지 않음 연산자(!=)[C#]"
  - "같지 않음 연산자(!=)[C#]"
ms.assetid: eeff7a4e-ad6f-462d-9f8d-49e9b91c6c97
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# != 연산자(C# 참조)
같지 않음 연산자\(`!=`\)는 피연산자가 같으면 false를 반환하고 그렇지 않으면 true를 반환합니다.  같지 않음 연산자는 문자열과 개체를 포함한 모든 형식에 대해 미리 정의되어 있습니다.  사용자 정의 형식으로 `!=` 연산자를 오버로드할 수 있습니다.  
  
## 설명  
 미리 정의된 값 형식의 경우 같지 않음 연산자\(`!=`\)는 피연산자의 값이 다르면 true를 반환하고 그렇지 않으면 false를 반환합니다.  `string` 형식을 제외한 참조 형식의 경우 `!=` 연산자는 두 피연산자가 서로 다른 개체를 참조하면 true를 반환합니다.  `string` 형식의 경우 `!=` 연산자는 문자열 값을 비교합니다.  
  
 사용자 정의 값 형식으로 `!=` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  사용자 정의 참조 형식으로도 오버로드할 수 있지만, 기본적으로 `!=` 연산자는 미리 정의된 형식과 사용자 정의 참조 형식 모두에 대해 위에서 설명한 것처럼 동작합니다.  `!=` 연산자를 오버로드할 경우에는 [\=\=](../../../csharp/language-reference/operators/equality-comparison-operator.md) 연산자도 오버로드해야 합니다.  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#33](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#33)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)