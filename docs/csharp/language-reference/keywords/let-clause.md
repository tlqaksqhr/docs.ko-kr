---
title: let 절(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: 9d625db1231687cdad2e24303b2e08ecf736a50c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33269642"
---
# <a name="let-clause-c-reference"></a>let 절(C# 참조)
쿼리 식에서 후속 절에 사용하기 위해 하위 식의 결과를 저장하면 유용한 경우가 있습니다. 새 범위 변수를 만들고 제공한 식의 결과로 초기화하는 `let` 키워드를 사용하면 이 작업을 수행할 수 있습니다. 값으로 초기화되면 범위 변수를 사용하여 다른 값을 저장할 수 없습니다. 그러나 범위 변수가 쿼리 가능 형식을 포함할 경우 쿼리할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서 `let`은 다음 두 가지 방법으로 사용됩니다.  
  
1.  그 자체를 쿼리할 수 있는 열거 가능한 형식을 만듭니다.  
  
2.  쿼리가 범위 변수 `word`에서 `ToLower`를 한 번만 호출할 수 있도록 합니다. `let`을 사용하지 않을 경우 `where` 절의 각 조건자에서 `ToLower`를 호출해야 합니다.  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [쿼리 키워드(LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [C#에서 LINQ 시작](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [방법: 쿼리 식의 예외 처리](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
