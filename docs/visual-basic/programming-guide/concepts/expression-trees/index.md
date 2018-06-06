---
title: 식 트리(Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8bbbb02d-7ffc-476b-8c25-118d82bf5d46
ms.openlocfilehash: babee41f7df48f270d0c56cb2af91e463407d5c1
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696951"
---
# <a name="expression-trees-visual-basic"></a><span data-ttu-id="871ec-102">식 트리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="871ec-102">Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="871ec-103">식 트리는 `x < y` 등의 이진 연산이나 메서드 호출과 같이 각 노드가 식인 트리 형식 데이터 구조의 코드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-103">Expression trees represent code in a tree-like data structure, where each node is an expression, for example, a method call or a binary operation such as `x < y`.</span></span>  
  
 <span data-ttu-id="871ec-104">식 트리로 표시되는 코드를 컴파일하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-104">You can compile and run code represented by expression trees.</span></span> <span data-ttu-id="871ec-105">이렇게 하면 실행 가능한 코드를 동적으로 수정하고, 다양한 데이터베이스에서 LINQ 쿼리를 실행하고, 동적 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-105">This enables dynamic modification of executable code, the execution of LINQ queries in various databases, and the creation of dynamic queries.</span></span> <span data-ttu-id="871ec-106">LINQ의 식 트리에 대한 자세한 내용은 [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)(방법: 식 트리를 사용하여 동적 쿼리 빌드(Visual Basic))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="871ec-106">For more information about expression trees in LINQ, see [How to: Use Expression Trees to Build Dynamic Queries (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md).</span></span>  
  
 <span data-ttu-id="871ec-107">식 트리는 동적 언어와 .NET Framework 간에 상호 운용성을 제공하고 컴파일러 작성기가 MSIL(Microsoft Intermediate Language) 대신 식 트리를 내보낼 수 있도록 DLR(동적 언어 런타임)에서도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-107">Expression trees are also used in the dynamic language runtime (DLR) to provide interoperability between dynamic languages and the .NET Framework and to enable compiler writers to emit expression trees instead of Microsoft intermediate language (MSIL).</span></span> <span data-ttu-id="871ec-108">DLR에 대한 자세한 내용은 [동적 언어 런타임 개요](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="871ec-108">For more information about the DLR, see [Dynamic Language Runtime Overview](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).</span></span>  
  
 <span data-ttu-id="871ec-109">익명 람다 식을 기준으로 C# 또는 Visual Basic 컴파일러가 식 트리를 자동으로 만들도록 할 수도 있고 <xref:System.Linq.Expressions> 네임스페이스를 사용하여 식 트리를 수동으로 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-109">You can have the C# or Visual Basic compiler create an expression tree for you based on an anonymous lambda expression, or you can create expression trees manually by using the <xref:System.Linq.Expressions> namespace.</span></span>  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a><span data-ttu-id="871ec-110">람다 식에서 식 트리 만들기</span><span class="sxs-lookup"><span data-stu-id="871ec-110">Creating Expression Trees from Lambda Expressions</span></span>  
 <span data-ttu-id="871ec-111">람다 식을 <xref:System.Linq.Expressions.Expression%601> 형식 변수에 할당하면 컴파일러가 해당 람다 식을 나타내는 식 트리를 작성하기 위해 코드를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-111">When a lambda expression is assigned to a variable of type <xref:System.Linq.Expressions.Expression%601>, the compiler emits code to build an expression tree that represents the lambda expression.</span></span>  
  
 <span data-ttu-id="871ec-112">Visual Basic 컴파일러는 람다 식(한 줄 람다)에서만 식 트리를 생성할 수 있으며</span><span class="sxs-lookup"><span data-stu-id="871ec-112">The Visual Basic compiler can generate expression trees only from expression lambdas (or single-line lambdas).</span></span> <span data-ttu-id="871ec-113">문 람다(여러 줄 람다)는 구문 분석할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-113">It cannot parse statement lambdas (or multi-line lambdas).</span></span> <span data-ttu-id="871ec-114">Visual Basic의 람다 식에 대한 자세한 내용은 [람다 식](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="871ec-114">For more information about lambda expressions in Visual Basic, see [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="871ec-115">다음 코드 예제에서는 Visual Basic 컴파일러가 람다 식 `Function(num) num < 5`를 나타내는 식 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-115">The following code examples demonstrate how to have the Visual Basic compiler create an expression tree that represents the lambda expression `Function(num) num < 5`.</span></span>  
  
```vb  
Dim lambda As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a><span data-ttu-id="871ec-116">API를 사용하여 식 트리 만들기</span><span class="sxs-lookup"><span data-stu-id="871ec-116">Creating Expression Trees by Using the API</span></span>  
 <span data-ttu-id="871ec-117">API를 사용하여 식 트리를 만들려면 <xref:System.Linq.Expressions.Expression> 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-117">To create expression trees by using the API, use the <xref:System.Linq.Expressions.Expression> class.</span></span> <span data-ttu-id="871ec-118">이 클래스는 변수나 매개 변수를 나타내는 <xref:System.Linq.Expressions.ParameterExpression> 또는 메서드 호출을 나타내는 <xref:System.Linq.Expressions.MethodCallExpression>과 같이 특정 형식의 식 트리 노드를 만드는 정적 팩터리 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-118">This class contains static factory methods that create expression tree nodes of specific types, for example, <xref:System.Linq.Expressions.ParameterExpression>, which represents a variable or parameter, or <xref:System.Linq.Expressions.MethodCallExpression>, which represents a method call.</span></span> <span data-ttu-id="871ec-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> 및 기타 식 관련 형식도 <xref:System.Linq.Expressions> 네임스페이스에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-119"><xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression>, and the other expression-specific types are also defined in the <xref:System.Linq.Expressions> namespace.</span></span> <span data-ttu-id="871ec-120">이러한 형식은 추상 형식 <xref:System.Linq.Expressions.Expression>에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-120">These types derive from the abstract type <xref:System.Linq.Expressions.Expression>.</span></span>  
  
 <span data-ttu-id="871ec-121">다음 코드 예제에서는 API를 사용하여 람다 식 `Function(num) num < 5`를 나타내는 식 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-121">The following code example demonstrates how to create an expression tree that represents the lambda expression `Function(num) num < 5` by using the API.</span></span>  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Manually build the expression tree for the lambda expression num => num < 5.  
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")  
Dim five As ConstantExpression = Expression.Constant(5, GetType(Integer))  
Dim numLessThanFive As BinaryExpression = Expression.LessThan(numParam, five)  
Dim lambda1 As Expression(Of Func(Of Integer, Boolean)) =  
  Expression.Lambda(Of Func(Of Integer, Boolean))(  
        numLessThanFive,  
        New ParameterExpression() {numParam})  
```  
  
 <span data-ttu-id="871ec-122">.NET Framework 4 이상에서는 식 트리 API가 루프, 조건부 블록, `try-catch` 블록 등의 할당 및 제어 흐름 식도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-122">In .NET Framework 4 or later, the expression trees API also supports assignments and control flow expressions such as loops, conditional blocks, and `try-catch` blocks.</span></span> <span data-ttu-id="871ec-123">API를 사용하면 Visual Basic 컴파일러를 통해 람다 식에서 작성할 수 있는 것보다 복잡한 식 트리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-123">By using the API, you can create expression trees that are more complex than those that can be created from lambda expressions by the Visual Basic compiler.</span></span> <span data-ttu-id="871ec-124">다음 예제에서는 숫자의 계승을 계산하는 식 트리를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-124">The following example demonstrates how to create an expression tree that calculates the factorial of a number.</span></span>  
  
```vb  
' Creating a parameter expression.  
Dim value As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "value")  
  
' Creating an expression to hold a local variable.   
Dim result As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "result")  
  
' Creating a label to jump to from a loop.  
Dim label As LabelTarget = Expression.Label(GetType(Integer))  
  
' Creating a method body.  
Dim block As BlockExpression = Expression.Block(  
    New ParameterExpression() {result},  
    Expression.Assign(result, Expression.Constant(1)),  
    Expression.Loop(  
        Expression.IfThenElse(  
            Expression.GreaterThan(value, Expression.Constant(1)),  
            Expression.MultiplyAssign(result,  
                Expression.PostDecrementAssign(value)),  
            Expression.Break(label, result)  
        ),  
        label  
    )  
)  
  
' Compile an expression tree and return a delegate.  
Dim factorial As Integer =  
    Expression.Lambda(Of Func(Of Integer, Integer))(block, value).Compile()(5)  
  
Console.WriteLine(factorial)  
' Prints 120.  
```

<span data-ttu-id="871ec-125">자세한 내용은 [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://blogs.msdn.microsoft.com/csharpfaq/2009/09/14/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010)(Visual Studio 2010에서 식 트리를 사용하여 동적 메서드 생성)을 참조하세요. 이 내용은 Visual Studio의 최신 버전에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-125">For more information, see [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://blogs.msdn.microsoft.com/csharpfaq/2009/09/14/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010), which also applies to later versions of Visual Studio.</span></span>
  
## <a name="parsing-expression-trees"></a><span data-ttu-id="871ec-126">식 트리 구문 분석</span><span class="sxs-lookup"><span data-stu-id="871ec-126">Parsing Expression Trees</span></span>  
 <span data-ttu-id="871ec-127">다음 코드 예제에서는 람다 식 `Function(num) num < 5`를 나타내는 식 트리를 개별 구성 요소로 구성 해제하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-127">The following code example demonstrates how the expression tree that represents the lambda expression `Function(num) num < 5` can be decomposed into its parts.</span></span>  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Create an expression tree.  
Dim exprTree As Expression(Of Func(Of Integer, Boolean)) = Function(num) num < 5  
  
' Decompose the expression tree.  
Dim param As ParameterExpression = exprTree.Parameters(0)  
Dim operation As BinaryExpression = exprTree.Body  
Dim left As ParameterExpression = operation.Left  
Dim right As ConstantExpression = operation.Right  
  
Console.WriteLine(String.Format("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value))  
  
' This code produces the following output:  
'  
' Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a><span data-ttu-id="871ec-128">변경 불가능한 식 트리</span><span class="sxs-lookup"><span data-stu-id="871ec-128">Immutability of Expression Trees</span></span>  
 <span data-ttu-id="871ec-129">식 트리는 변경할 수 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-129">Expression trees should be immutable.</span></span> <span data-ttu-id="871ec-130">즉, 식 트리를 수정하려면 기존 식 트리를 복사한 다음 트리 내의 노드를 바꾸는 방법으로 새 식 트리를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-130">This means that if you want to modify an expression tree, you must construct a new expression tree by copying the existing one and replacing nodes in it.</span></span> <span data-ttu-id="871ec-131">식 트리 방문자를 사용하면 기존 식 트리를 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-131">You can use an expression tree visitor to traverse the existing expression tree.</span></span> <span data-ttu-id="871ec-132">자세한 내용은 [방법: 식 트리 수정(Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="871ec-132">For more information, see [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md).</span></span>  
  
## <a name="compiling-expression-trees"></a><span data-ttu-id="871ec-133">식 트리 컴파일</span><span class="sxs-lookup"><span data-stu-id="871ec-133">Compiling Expression Trees</span></span>  
 <span data-ttu-id="871ec-134"><xref:System.Linq.Expressions.Expression%601> 형식은 식 트리로 표시되는 코드를 실행 가능한 대리자로 컴파일하는 <xref:System.Linq.Expressions.Expression%601.Compile%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-134">The <xref:System.Linq.Expressions.Expression%601> type provides the <xref:System.Linq.Expressions.Expression%601.Compile%2A> method that compiles the code represented by an expression tree into an executable delegate.</span></span>  
  
 <span data-ttu-id="871ec-135">다음 코드 예제에서는 식 트리를 컴파일하고 결과 코드를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-135">The following code example demonstrates how to compile an expression tree and run the resulting code.</span></span>  
  
```vb  
' Creating an expression tree.  
Dim expr As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
  
' Compiling the expression tree into a delegate.  
Dim result As Func(Of Integer, Boolean) = expr.Compile()  
  
' Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4))  
  
' Prints True.  
  
' You can also use simplified syntax  
' to compile and run an expression tree.  
' The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4))  
  
' Also prints True.  
```  
  
 <span data-ttu-id="871ec-136">자세한 내용은 [방법: 식 트리 실행(Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="871ec-136">For more information, see [How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="871ec-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="871ec-137">See Also</span></span>  
 <xref:System.Linq.Expressions>  
 [<span data-ttu-id="871ec-138">방법: 식 트리 (Visual Basic)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-138">How to: Execute Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)  
 [<span data-ttu-id="871ec-139">방법: 식 트리 (Visual Basic)를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="871ec-139">How to: Modify Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)  
 [<span data-ttu-id="871ec-140">람다 식</span><span class="sxs-lookup"><span data-stu-id="871ec-140">Lambda Expressions</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="871ec-141">동적 언어 런타임 개요</span><span class="sxs-lookup"><span data-stu-id="871ec-141">Dynamic Language Runtime Overview</span></span>](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)  
 [<span data-ttu-id="871ec-142">프로그래밍 개념(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="871ec-142">Programming Concepts (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
