---
title: "방법: 쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "암시적으로 형식화된 지역 변수[C#], 사용 방법"
ms.assetid: 6b7354d2-af79-427a-b6a8-f74eb8fd0b91
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# 방법: 쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열 사용(C# 프로그래밍 가이드)
컴파일러가 지역 변수의 형식을 확인하도록 하려고 할 때마다 암시적으로 형식화된 지역 변수를 사용할 수 있습니다.  쿼리 식에서 자주 사용되는 익명 형식을 저장하려면 암시적으로 형식화된 지역 변수를 사용해야 합니다.  다음 예제에서는 암시적으로 형식화된 지역 변수를 쿼리에 선택적으로 사용할 수 있는 경우와 필수적으로 사용해야 하는 경우를 모두 보여 줍니다.  
  
 암시적으로 형식화된 지역 변수는 [var](../../../csharp/language-reference/keywords/var.md) 컨텍스트 키워드를 사용하여 선언됩니다.  자세한 내용은 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) 및 [암시적으로 형식화된 배열](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `var` 키워드가 필요한 일반적인 시나리오 즉, 익명 형식의 시퀀스를 생성하는 쿼리 식을 보여 줍니다.  이 시나리오에서는 사용자에게 익명 형식의 형식 이름에 대한 액세스 권한이 없기 때문에 쿼리 변수와 `foreach` 문의 반복 변수 모두 `var`를 사용하여 암시적으로 형식화되어야 합니다.  익명 형식에 대한 자세한 내용은 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하십시오.  
  
 [!code-cs[csProgGuideLINQ#32](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_1.cs)]  
  
## 예제  
 다음 예제에서는 비슷한 상황이지만 `var` 사용이 선택적인 상황에서 `var` 키워드가 사용됩니다.  `student.LastName`이 문자열이므로 쿼리를 실행하면 문자열의 시퀀스가 반환됩니다.  따라서 `queryID`의 형식을 `var` 대신 `System.Collections.Generic.IEnumerable<string>`으로 선언할 수 있습니다.  `var` 키워드는 편의를 위해 사용됩니다.  예제에서 `foreach` 문의 반복 변수는 명시적으로 문자열로 형식화되지만 대신 `var`를 사용하여 선언될 수도 있습니다.  반복 변수의 형식은 익명 형식이 아니기 때문에 `var` 사용은 필수가 아닌 선택입니다.  `var` 자체는 형식이 아니라 컴파일러가 형식을 유추하고 할당하도록 지정하는 명령입니다.  
  
 [!code-cs[csProgGuideLINQ#33](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression_2.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [확장 메서드](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)