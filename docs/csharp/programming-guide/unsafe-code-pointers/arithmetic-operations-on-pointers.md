---
title: "포인터에 대한 산술 연산(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "포인터[C#], 산술 연산자"
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# 포인터에 대한 산술 연산(C# 프로그래밍 가이드)
이 항목에서는 `+` 및 **\-** 산술 연산자를 사용하여 포인터를 조작하는 방법에 대해 설명합니다.  
  
> [!NOTE]
>  void 포인터에는 산술 연산을 수행할 수 없습니다.  
  
## 숫자 값을 포인터에 더하기 및 포인터에서 빼기  
 `void*`를 제외한 모든 형식의 포인터 `p`, `` 에 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) 또는 [ulong](../../../csharp/language-reference/keywords/ulong.md) 형식의 `n` 값을 더할 수 있습니다.  결과 `p+n`은 `n * sizeof(p)`를 p의 주소에 더하여 만들어지는 포인터입니다.  마찬가지로 `p-n`은 `p`의 주소에서 `n * sizeof(p)`를 빼서 만들어지는 포인터입니다.  
  
## 포인터 빼기  
 동일한 형식의 포인터끼리 뺄 수도 있습니다.  결과의 형식은 항상 `long`입니다.  예를 들어 `p1`과 `p2`가 `pointer-type*` 형식의 포인터이면 `p1-p2` 식의 결과는 다음과 같습니다.  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 산술 연산이 포인터의 도메인에서 오버플로되어도 예외는 발생하지 않으며, 연산의 결과는 구현에 따라 다릅니다.  
  
## 예제  
 [!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md)   
 [포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [포인터 조작](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)   
 [포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)   
 [형식](../../../csharp/language-reference/keywords/types.md)   
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)   
 [fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md)   
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)