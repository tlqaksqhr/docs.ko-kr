---
title: '방법: 식 트리 실행(C#)'
ms.date: 07/20/2015
ms.assetid: b8c40db5-2464-4bb9-9001-8c2bc7f006c5
ms.openlocfilehash: 0ebdcb603a1adf3602e897db284faa2f75b7de7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322093"
---
# <a name="how-to-execute-expression-trees-c"></a><span data-ttu-id="567d1-102">방법: 식 트리 실행(C#)</span><span class="sxs-lookup"><span data-stu-id="567d1-102">How to: Execute Expression Trees (C#)</span></span>
<span data-ttu-id="567d1-103">이 항목에서는 식 트리를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="567d1-104">식 트리를 실행할 때 값이 반환될 수 있거나, 메서드 호출 등의 작업만 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="567d1-105">람다 식을 나타내는 식 트리만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="567d1-106">람다 식을 나타내는 식 트리는 <xref:System.Linq.Expressions.LambdaExpression> 또는 <xref:System.Linq.Expressions.Expression%601> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="567d1-107">이러한 식 트리를 실행하려면 <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> 메서드를 호출하여 실행 가능한 대리자를 만든 후 대리자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="567d1-108">대리자의 형식을 알 수 없는 경우, 즉 람다 식이 <xref:System.Linq.Expressions.Expression%601> 형식이 아니라 <xref:System.Linq.Expressions.LambdaExpression> 형식인 경우 대리자를 직접 호출하는 대신 대리자의 <xref:System.Delegate.DynamicInvoke%2A> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="567d1-109">식 트리가 람다 식을 나타내지 않는 경우 <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> 메서드를 호출하여 원래 식 트리가 본문으로 포함된 새 람다 식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="567d1-110">그런 다음 이 섹션의 앞부분에서 설명한 대로 람다 식을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="567d1-111">예</span><span class="sxs-lookup"><span data-stu-id="567d1-111">Example</span></span>  
 <span data-ttu-id="567d1-112">다음 코드 예제에서는 람다 식을 만들고 실행하여 숫자의 거듭제곱을 나타내는 식 트리를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="567d1-113">숫자의 거듭제곱을 나타내는 결과가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```csharp  
// The expression tree to execute.  
BinaryExpression be = Expression.Power(Expression.Constant(2D), Expression.Constant(3D));  
  
// Create a lambda expression.  
Expression<Func<double>> le = Expression.Lambda<Func<double>>(be);  
  
// Compile the lambda expression.  
Func<double> compiledExpression = le.Compile();  
  
// Execute the lambda expression.  
double result = compiledExpression();  
  
// Display the result.  
Console.WriteLine(result);  
  
// This code produces the following output:  
// 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="567d1-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="567d1-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="567d1-115">아직 참조되지 않는 경우 System.Core.dll에 대한 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="567d1-116">System.Linq.Expressions 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="567d1-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="567d1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="567d1-117">See Also</span></span>  
 [<span data-ttu-id="567d1-118">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="567d1-118">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)  
 [<span data-ttu-id="567d1-119">방법: 식 트리 수정(C#)</span><span class="sxs-lookup"><span data-stu-id="567d1-119">How to: Modify Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
