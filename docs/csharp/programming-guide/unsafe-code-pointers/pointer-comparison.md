---
title: "포인터 비교(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "포인터[C#], 비교"
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 포인터 비교(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다음과 같은 연산자를 사용하여 모든 형식의 포인터를 비교할 수 있습니다.  
  
 **\=\=   \!\=   \<   \>   \<\=   \>\=**  
  
 비교 연산자는 두 피연산자에 있는 주소 값을 부호 없는 정수처럼 비교합니다.  
  
## 예제  
 [!CODE [csProgGuidePointers#16](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#16)]  
  
 [!CODE [csProgGuidePointers#17](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#17)]  
  
## 샘플 출력  
 `True`  
  
 `False`  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [포인터 조작](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)