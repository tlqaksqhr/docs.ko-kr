---
title: "#else(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "#else"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "#else 지시문[C#]"
ms.assetid: 6a347322-cfa2-4a86-98f8-ddfa2cb7d4db
caps.latest.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 11
---
# #else(C# 참조)
`#else`를 사용하여 복합 조건부 지시문을 만들 수 있습니다. 이때 앞의 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 또는 [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md)\(선택적 요소\) 지시문에 있는 식이 어느 것도 `true`가 아닌 경우 컴파일러는 `#else`와 이후의 `#endif` 사이의 모든 코드를 계산합니다.  
  
## 설명  
 [\#endif](../../../csharp/language-reference/preprocessor-directives/preprocessor-endif.md)는 `#else` 다음에 오는 전처리기 지시문이어야 합니다.  `#else` 사용 방법 예제는 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 전처리기 지시문](../../../csharp/language-reference/preprocessor-directives/index.md)