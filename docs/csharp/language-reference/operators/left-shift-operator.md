---
title: "&lt;&lt; 연산자(C# 참조) | Microsoft Docs"
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
  - "<<_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "<< 연산자[C#]"
  - "왼쪽 시프트 연산자(<<)[C#]"
ms.assetid: a654eb56-1ff7-4bf3-9064-b631be0cdccc
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# &lt;&lt; 연산자(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

왼쪽 시프트 연산자\(`<<`\)는 첫째 피연산자를 둘째 피연산자에서 지정한 비트 수만큼 비트 단위로 왼쪽으로 이동합니다.  두 번째 피연산자의 형식은 [int](../../../csharp/language-reference/keywords/int.md) 또는 `int`에 대한 미리 정의된 암시적 숫자 변환이 있는 형식이어야 합니다.  
  
## 설명  
 첫째 피연산자가 32비트 용량의 [int](../../../csharp/language-reference/keywords/int.md) 또는 [uint](../../../csharp/language-reference/keywords/uint.md) 형식이면 시프트 횟수는 둘째 피연산자의 하위 5비트로 지정됩니다.  즉, 실제 시프트 횟수는 0\-31 비트입니다.  
  
 첫째 피연산자가 64비트 용량의 [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식이면 시프트 횟수는 둘째 피연산자의 하위 6비트로 지정됩니다.  즉, 실제 시프트 횟수는 0\-63 비트입니다.  
  
 시프트 후 첫 번째 피연산자의 형식 범위 내에 없는 상위 비트는 무시되고 하위의 빈 비트는 0으로 채워집니다.  시프트 연산은 오버플로를 일으키지 않습니다.  
  
 사용자 정의 형식으로 `<<` 연산자를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\). 이 경우, 첫째 피연산자의 형식은 사용자 정의 형식이어야 하며 둘째 피연산자의 형식은 `int`여야 합니다.  이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## 예제  
 [!CODE [csRefOperators#14](../CodeSnippet/VS_Snippets_VBCSharp/csrefOperators#14)]  
  
## 설명  
 1과 33은 하위 5비트가 같기 때문에 `i<<1`과 `i<<33` 의 결과는 같습니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)