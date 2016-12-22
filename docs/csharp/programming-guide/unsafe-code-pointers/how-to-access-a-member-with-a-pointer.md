---
title: "방법: 포인터로 멤버 액세스(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "포인터[C#], 멤버 액세스"
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 포인터로 멤버 액세스(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

안전하지 않은 컨텍스트에 선언된 구조체의 멤버에 액세스하려면 다음 예제와 같이 멤버 액세스 연산자를 사용합니다. 이 예제에서 `p`는 `x` 멤버가 포함된 [구조체](../../../csharp/language-reference/keywords/struct.md)에 대한 포인터입니다.  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## 예제  
 이 예제에서는 `x` 및 `y`라는 두 좌표가 포함된 `CoOrds`라는 [구조체](../../../csharp/language-reference/keywords/struct.md)를 선언하고 인스턴스화합니다.  `->` 멤버 액세스 연산자와 `home` 인스턴스에 대한 포인터를 사용하여 `x` 및 `y`에 값을 대입합니다.  
  
> [!NOTE]
>  `p->x` 식은 `(*p).x` 식과 동일하며 두 식 중 어느 식을 사용해도 같은 결과를 얻을 수 있습니다.  
  
 [!CODE [csProgGuidePointers#9](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#9)]  
  
 [!CODE [csProgGuidePointers#10](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#10)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)