---
title: "var(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "var"
  - "var_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "var 키워드[C#]"
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 13
---
# var(C# 참조)
Visual C\# 3.0부터는 메서드 범위에서 선언된 변수가 암시적 형식 `var`를 가질 수 있습니다.  암시적으로 형식화된 지역 변수는 형식 자체를 선언했던 것처럼 강력하게 형식화되었지만 컴파일러에서 형식을 결정합니다.  다음의 `i`의 두 선언은 기능면에서 동일합니다.  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 자세한 내용은 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) 및 [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 두 개의 쿼리 식을 보여 줍니다.  첫 번째 식에서 `var`의 사용은 허용되나 쿼리 결과의 형식이 `IEnumerable<string>`로 명확하게 지정되기 때문에 필요한 것은 아닙니다.  그러나 두 번째 식에서는 결과가 익명 형식의 컬렉션이고 형식의 이름이 컴파일러 자체 이외에는 액세스할 수 없으므로 `var`를 사용해야 합니다.  예제 \#2에서 `foreach` 반복 변수 `item`은 암시적으로도 형식화되어야 합니다.  
  
 [!code-cs[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/csharp/var_1.cs)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [암시적으로 형식화한 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)