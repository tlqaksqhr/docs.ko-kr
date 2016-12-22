---
title: "방법: 포인터 증가 및 감소(C# 프로그래밍 가이드) | Microsoft Docs"
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
  - "포인터 식[C#], 증가 및 감소"
  - "포인터[C#], 증가 및 감소"
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 포인터 증가 및 감소(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

증가 및 감소 연산자인 `++` 및 `--` 연산자를 사용하면 pointer\-type\*형식의 포인터에 대해 [sizeof](../../../csharp/language-reference/keywords/sizeof.md)\(`pointer-type`\)만큼 포인터 위치를 변경할 수 있습니다.  증가 및 감소 식의 형태는 다음과 같습니다.  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 증가 및 감소 연산자는 `void*` 형식을 제외한 모든 형식의 포인터에 적용할 수 있습니다.  
  
 `pointer-type` 형식의 포인터에 증가 연산자를 적용하면 포인터 변수에 포함된 주소에 [sizeof](../../../csharp/language-reference/keywords/sizeof.md)\(`pointer-type`\)가 더해집니다.  
  
 `pointer-type` 형식의 포인터에 감소 연산자를 적용하면 포인터 변수에 포함된 주소가 `sizeof`\(`pointer-type`\)만큼 감소합니다.  
  
 연산이 포인터의 도메인에서 오버플로되어도 예외는 발생하지 않으며, 연산의 결과는 구현에 따라 다릅니다.  
  
## 예제  
 이 예제에서는 포인터를 `int`의 크기만큼 증가시키면서 배열의 요소를 차례로 표시합니다.  포인터가 증가할 때마다 배열 요소의 내용 및 주소가 표시됩니다.  
  
 [!CODE [csProgGuidePointers#3](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#3)]  
  
 [!CODE [csProgGuidePointers#13](../CodeSnippet/VS_Snippets_VBCSharp/csProgGuidePointers#13)]  
  
  **Value:0 @ Address:12860272**  
**Value:1 @ Address:12860276**  
**Value:2 @ Address:12860280**  
**Value:3 @ Address:12860284**  
**Value:4 @ Address:12860288**   
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