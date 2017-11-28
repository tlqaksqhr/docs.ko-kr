---
title: "var(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords: var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2be56243f9c4ddafb3903d14fa6d6f9cb0e2f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="var-c-reference"></a>var(C# 참조)
Visual C# 3.0부터 메서드 범위에서 선언된 변수에 암시적 "형식" `var`을 사용할 수 있습니다. 암시적 형식 지역 변수는 형식을 직접 선언한 것처럼 강력한 형식이지만 컴파일러가 형식을 결정합니다. `i`의 다음 두 선언은 기능이 동일합니다.  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 자세한 내용은 [암시적 형식 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) 및 [LINQ 쿼리 작업의 형식 관계](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 두 가지 쿼리 식을 보여 줍니다. 첫 번째 식에서는 `var`을 사용할 수 있지만, 쿼리 결과의 형식을 `IEnumerable<string>`으로 명시적으로 정의할 수 있기 때문에 필요하지 않습니다. 그러나 두 번째 식에서는 결과가 무명 형식의 컬렉션이고 컴파일러 자체를 제외하고 해당 형식의 이름에 액세스할 수 없기 때문에 `var`을 사용해야 합니다. 예제 #2에서는 `foreach` 반복 변수 `item`도 암시적 형식이어야 합니다.  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [암시적 형식 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
