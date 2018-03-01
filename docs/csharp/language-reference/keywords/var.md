---
title: "var(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2be56243f9c4ddafb3903d14fa6d6f9cb0e2f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="var-c-reference"></a><span data-ttu-id="e7025-102">var(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e7025-102">var (C# Reference)</span></span>
<span data-ttu-id="e7025-103">Visual C# 3.0부터 메서드 범위에서 선언된 변수에 암시적 "형식" `var`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7025-103">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="e7025-104">암시적 형식 지역 변수는 형식을 직접 선언한 것처럼 강력한 형식이지만 컴파일러가 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="e7025-104">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="e7025-105">`i`의 다음 두 선언은 기능이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e7025-105">The following two declarations of `i` are functionally equivalent:</span></span>  
  
```  
var i = 10; // implicitly typed  
int i = 10; //explicitly typed  
```  
  
 <span data-ttu-id="e7025-106">자세한 내용은 [암시적 형식 지역 변수](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) 및 [LINQ 쿼리 작업의 형식 관계](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e7025-106">For more information, see [Implicitly Typed Local Variables](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7025-107">예제</span><span class="sxs-lookup"><span data-stu-id="e7025-107">Example</span></span>  
 <span data-ttu-id="e7025-108">다음 예제에서는 두 가지 쿼리 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e7025-108">The following example shows two query expressions.</span></span> <span data-ttu-id="e7025-109">첫 번째 식에서는 `var`을 사용할 수 있지만, 쿼리 결과의 형식을 `IEnumerable<string>`으로 명시적으로 정의할 수 있기 때문에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e7025-109">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="e7025-110">그러나 두 번째 식에서는 결과가 무명 형식의 컬렉션이고 컴파일러 자체를 제외하고 해당 형식의 이름에 액세스할 수 없기 때문에 `var`을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7025-110">However, in the second expression, `var` must be used because the result is a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="e7025-111">예제 #2에서는 `foreach` 반복 변수 `item`도 암시적 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7025-111">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#18](../../../csharp/language-reference/keywords/codesnippet/CSharp/var_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="e7025-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7025-112">See Also</span></span>  
 [<span data-ttu-id="e7025-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e7025-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="e7025-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e7025-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e7025-115">암시적 형식 지역 변수</span><span class="sxs-lookup"><span data-stu-id="e7025-115">Implicitly Typed Local Variables</span></span>](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
