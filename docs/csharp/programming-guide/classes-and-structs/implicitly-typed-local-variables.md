---
title: "암시적으로 형식화된 지역 변수(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "암시적으로 형식화된 지역 변수[C#]"
  - "var[C#]"
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
caps.latest.revision: 23
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 암시적으로 형식화된 지역 변수(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

지역 변수에 명시적 형식 대신 유추된 `var` "형식"을 지정할 수 있습니다.  `var` 키워드는 초기화 문의 오른쪽에 있는 식에서 변수 형식을 유추하도록 컴파일러에 지시합니다.  유추된 형식은 기본 제공 형식, 익명 형식, 사용자 정의 형식 또는 .NET Framework 클래스 라이브러리에서 정의된 형식일 수 있습니다.  `var`을 사용하여 배열을 초기화하는 방법에 대한 자세한 내용은 [암시적으로 형식화된 배열](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)을 참조하십시오.  
  
 다음 예제에서는 `var`을 사용하여 지역 변수를 선언할 수 있는 다양한 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 `var` 키워드는 "variant"를 의미하지 않으며 변수가 느슨한 형식이거나 런타임에 바인딩됨을 나타내지 않습니다.  이 키워드는 단지 컴파일러에서 가장 적합한 형식을 결정하여 할당한다는 것을 의미합니다.  
  
 `var` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
-   앞의 예제에서 표시된 것처럼 지역 변수\(메서드 범위에서 선언된 변수\)에서  
  
-   [for](../../../csharp/language-reference/keywords/for.md) 초기화 문에서  
  
    ```  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 초기화 문에서  
  
    ```  
    foreach(var item in list){...}  
    ```  
  
-   [using 문](../../../visual-basic/language-reference/statements/using-statement.md)에서  
  
    ```  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 자세한 내용은 [방법: 쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열 사용](../Topic/How%20to:%20Use%20Implicitly%20Typed%20Local%20Variables%20and%20Arrays%20in%20a%20Query%20Expression%20\(C%23%20Programming%20Guide\).md)를 참조하십시오.  
  
## var 및 익명 형식  
 대부분의 경우 `var` 사용은 선택 사항이며 단지 구문상 편의를 위해 사용됩니다.  하지만 변수가 익명 형식으로 초기화되는 경우 나중에 개체의 속성에 액세스해야 하면 변수를 `var`로 선언해야 합니다.  이는 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] 쿼리 식의 일반적인 시나리오입니다.  자세한 내용은 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하십시오.  
  
 소스 코드의 관점에서 보면 익명 형식에는 이름이 없습니다.  따라서 쿼리 변수가 `var`로 초기화된 경우 반환된 개체 시퀀스에서 속성에 액세스하는 유일한 방법은 `foreach` 문에서 반복 변수의 형식으로 `var`을 사용하는 것입니다.  
  
 [!code-cs[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## 설명  
 암시적으로 형식화된 선언에는 다음과 같은 제한 사항이 있습니다.  
  
-   `var`은 동일한 문에서 지역 변수를 선언하고 초기화하는 경우에만 사용할 수 있습니다. 변수를 null, 메서드 그룹 또는 익명 함수로 초기화할 수 없습니다.  
  
-   `var`은 클래스 범위의 필드에서 사용할 수 없습니다.  
  
-   `var`을 사용하여 선언된 변수는 초기화 식에서 사용할 수 없습니다.  즉 `: int i = (i = 20);` 식은 문제가 없지만 이 식에서는 컴파일 타임 오류인 `var i = (i = 20);`가 발생합니다.  
  
-   암시적으로 형식화된 여러 변수를 동일한 문에서 초기화할 수 없습니다.  
  
-   `var`이라는 이름의 형식이 범위에 있으면 `var` 키워드는 해당 형식 이름으로 확인되며 암시적으로 형식화된 지역 변수 선언의 일부로 처리되지 않습니다.  
  
 `var`은 쿼리 변수의 생성된 형식을 정확하게 확인하기 어려운 쿼리 식에서 유용할 수도 있습니다.  그룹화 및 정렬 작업에서 이러한 경우가 발생할 수 있습니다.  
  
 `var` 키워드는 특정 변수 형식이 키보드에서 형식화하기 번거롭거나 명백하거나 코드 가독성에 도움이 되지 않는 경우에도 유용할 수 있습니다.  `var`이 이런 방식으로 유용한 한 가지 예제로 그룹 작업에 사용되는 형식과 같은 중첩 제네릭 형식이 있습니다.  다음 쿼리에서 쿼리 변수의 형식은 `IEnumerable<IGrouping<string, Student>>`입니다.  사용자 및 코드를 유지 관리해야 하는 다른 사용자를 이를 이해하기만 하면 간편하게 암시적 형식화를 사용하는 데 아무 문제도 없습니다.  
  
 [!CODE [cscsrefQueryKeywords#13](../CodeSnippet/VS_Snippets_VBCSharp/CsCsrefQueryKeywords#13)]  
  
 그러나 `var`을 사용하면 다른 개발자가 코드를 이해하는 것이 더 어려워질 수 있습니다.  이런 이유로 C\# 문서에서는 일반적으로 필요한 경우에만 `var`을 사용합니다.  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [암시적으로 형식화된 배열](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)   
 [방법: 쿼리 식에서 암시적으로 형식화된 지역 변수 및 배열 사용](../Topic/How%20to:%20Use%20Implicitly%20Typed%20Local%20Variables%20and%20Arrays%20in%20a%20Query%20Expression%20\(C%23%20Programming%20Guide\).md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)   
 [var](../../../csharp/language-reference/keywords/var.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [for](../../../csharp/language-reference/keywords/for.md)   
 [foreach, in](../../../csharp/language-reference/keywords/foreach-in.md)   
 [using 문](../../../visual-basic/language-reference/statements/using-statement.md)