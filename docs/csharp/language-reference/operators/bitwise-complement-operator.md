---
title: "~ 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "~_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "~[C#], 비트 보수 연산자"
  - "~ 연산자[C#]"
  - "비트 보수 연산자[C#]"
  - "물결표(~) 보수 연산자[C#]"
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# ~ 연산자(C# 참조)
`~` 연산자는 피연산자에 대한 비트 보수 연산을 수행하여 각 비트를 반전시킵니다.  비트 보수 연산자는 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) 및 [ulong](../../../csharp/language-reference/keywords/ulong.md)에 대해 미리 정의되어 있습니다.  
  
> [!NOTE]
>  `~` 기호는 소멸자를 선언하는 데에도 사용됩니다.  자세한 내용은 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)를 참조하십시오.  
  
## 설명  
 사용자 정의 형식으로 `~`  연산자를 오버로드할 수 있습니다.  자세한 내용은 [연산자](../../../csharp/language-reference/keywords/operator.md)를 참조하십시오.  정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.  
  
## 예제  
 [!code-cs[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#25)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)   
 [소멸자](../../../csharp/programming-guide/classes-and-structs/destructors.md)