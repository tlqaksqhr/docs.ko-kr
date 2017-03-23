---
title: "암시적으로 형식화된 배열(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "배열[C#], 암시적으로 형식화된"
  - "C# 언어, 암시적으로 형식화된 배열"
  - "암시적으로 형식화된 배열[C#]"
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# 암시적으로 형식화된 배열(C# 프로그래밍 가이드)
배열 이니셜라이저에 지정된 요소에서 배열 인스턴스의 형식을 유추한 암시적으로 형식화된 배열을 만들 수 있습니다.  또한 암시적으로 형식화된 변수에 대한 규칙은 암시적으로 형식화된 배열에 적용됩니다.  자세한 내용은 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하십시오.  
  
 암시적으로 형식화된 배열은 대개 익명 형식과 개체 및 컬렉션 이니셜라이저와 함께 쿼리 식에 사용됩니다.  
  
 다음 예제에서는 암시적으로 형식화된 배열을 만드는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideLINQ#37](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_1.cs)]  
  
 앞의 예제에서 암시적으로 형식화된 배열과 함께 대괄호는 초기화 문의 왼쪽에 사용되지 않습니다.  또한 가변 배열은 1차원 배열처럼 `new []`를 사용하여 초기화됩니다.  
  
## 개체 이니셜라이저에서 암시적으로 형식화된 배열  
 배열을 포함하는 익명 형식을 만들어야 하는 경우 배열은 형식의 개체 이니셜라이저에서 암시적으로 형식화되어야 합니다.  다음 예제에서 `contacts`는 `PhoneNumbers`라는 이름의 배열을 포함하는 각 익명 형식의 암시적으로 형식화된 배열입니다.  `var` 키워드는 개체 이니셜라이저 내부에서 사용되지 않습니다.  
  
 [!code-cs[csProgGuideLINQ#38](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-arrays_2.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)   
 [배열](../../../csharp/programming-guide/arrays/index.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)