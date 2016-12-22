---
title: "&amp;&amp; 연산자(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "&&_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "&& 연산자[C#]"
  - "논리곱 연산자[C#]"
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &amp;&amp; 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

조건부 논리 AND 연산자\(`&&`\)는 `bool` 피연산자의 논리 AND를 수행하지만 둘째 피연산자는 필요한 경우에만 계산합니다.  
  
## 설명  
 아래 연산은  
  
```  
x && y  
```  
  
 다음 연산에 해당하지만  
  
```  
x & y  
```  
  
 경우를 제외 하 고 `x` 입니다 `false`, `y` AND 연산의 결과 이기 때문에 계산 되지 않습니다 `false` 의 어떤 값에 관계 없이 `y`  입니다.  이것을 "단락\(short\-circuit\)" 계산이라고 합니다.  
  
 조건부 논리 AND 연산자는 오버로드할 수 없지만, 일반적인 논리 연산자와 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md) 연산자의 오버로드가 조건부 논리 연산자의 오버로드로 간주됩니다. 이 경우 일부 제한이 있습니다.  
  
## 예제  
 다음 예제에서는 조건식에 두 번째 `if` 문이 평가 되는 첫 번째 피연산자가 피연산자를 반환 하기 때문에 `false`.  
  
 [!CODE [csRefOperators#48](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#48)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)