---
title: "&amp;= 연산자(C# 참조) | Microsoft Docs"
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
  - "&=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "&= 연산자[C#]"
  - "AND 대입 연산자(&=)[C#]"
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
caps.handback.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &amp;= 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

AND 대입 연산자입니다.  
  
## 설명  
 다음과 같이 `&=` 대입 연산자를 사용하는 식은  
  
```  
x &= y  
```  
  
 동일한 함수는  
  
```  
x = x & y  
```  
  
 그러나 `x`가 한 번만 계산된다는 점은 다릅니다.  [& 연산자](../../../visual-basic/language-reference/operators/and-operator.md)는 정수 계열 피연산자에 대해서는 비트 논리 AND 연산을 수행하고, `bool` 피연산자에 대해서는 논리 AND 연산을 수행합니다.  
  
 `&=` 연산자는 직접 오버로드될 수 없지만 사용자 정의 형식으로 이항 [& 연산자](../../../visual-basic/language-reference/operators/and-operator.md)를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  
  
## 예제  
 [!CODE [csRefOperators#34](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#34)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)