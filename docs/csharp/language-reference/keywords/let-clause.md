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
---
# <a name="let-clause-c-reference"></a><span data-ttu-id="46f81-102">let 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="46f81-102">let clause (C# Reference)</span></span>
<span data-ttu-id="46f81-103">쿼리 식에서 후속 절에 사용하기 위해 하위 식의 결과를 저장하면 유용한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-103">In a query expression, it is sometimes useful to store the result of a sub-expression in order to use it in subsequent clauses.</span></span> <span data-ttu-id="46f81-104">새 범위 변수를 만들고 제공한 식의 결과로 초기화하는 `let` 키워드를 사용하면 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-104">You can do this with the `let` keyword, which creates a new range variable and initializes it with the result of the expression you supply.</span></span> <span data-ttu-id="46f81-105">값으로 초기화되면 범위 변수를 사용하여 다른 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-105">Once initialized with a value, the range variable cannot be used to store another value.</span></span> <span data-ttu-id="46f81-106">그러나 범위 변수가 쿼리 가능 형식을 포함할 경우 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-106">However, if the range variable holds a queryable type, it can be queried.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46f81-107">예</span><span class="sxs-lookup"><span data-stu-id="46f81-107">Example</span></span>  
 <span data-ttu-id="46f81-108">다음 예제에서 `let`은 다음 두 가지 방법으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-108">In the following example `let` is used in two ways:</span></span>  
  
1.  <span data-ttu-id="46f81-109">그 자체를 쿼리할 수 있는 열거 가능한 형식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-109">To create an enumerable type that can itself be queried.</span></span>  
  
2.  <span data-ttu-id="46f81-110">쿼리가 범위 변수 `word`에서 `ToLower`를 한 번만 호출할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-110">To enable the query to call `ToLower` only one time on the range variable `word`.</span></span> <span data-ttu-id="46f81-111">`let`을 사용하지 않을 경우 `where` 절의 각 조건자에서 `ToLower`를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46f81-111">Without using `let`, you would have to call `ToLower` in each predicate in the `where` clause.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#28](../../../csharp/language-reference/keywords/codesnippet/CSharp/let-clause_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="46f81-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46f81-112">See Also</span></span>  
 [<span data-ttu-id="46f81-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="46f81-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="46f81-114">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="46f81-114">Query Keywords (LINQ)</span></span>](../../../csharp/language-reference/keywords/query-keywords.md)  
 [<span data-ttu-id="46f81-115">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="46f81-115">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="46f81-116">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="46f81-116">Getting Started with LINQ in C#</span></span>](../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [<span data-ttu-id="46f81-117">방법: 쿼리 식의 예외 처리</span><span class="sxs-lookup"><span data-stu-id="46f81-117">How to: Handle Exceptions in Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/how-to-handle-exceptions-in-query-expressions.md)
