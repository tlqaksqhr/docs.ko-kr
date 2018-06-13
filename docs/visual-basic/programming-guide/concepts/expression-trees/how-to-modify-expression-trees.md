---
title: '방법: 식 트리 (Visual Basic)를 수정 합니다.'
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: 92a0fb37e2a383c68beb2e4a56deb16f89a9bd28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643878"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="0fe08-102">방법: 식 트리 (Visual Basic)를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="0fe08-103">이 항목에서는 식 트리를 수정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="0fe08-104">식 트리는 변경할 수 없으며, 직접 수정할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="0fe08-105">식 트리를 변경하려면 기존 식 트리의 복사본을 만들고, 해당 복사본을 만들 때 필요한 사항을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="0fe08-106"><xref:System.Linq.Expressions.ExpressionVisitor> 클래스를 사용하여 기존 식 트리를 트래버스하고 방문하는 각 노드를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="0fe08-107">식 트리를 수정하려면</span><span class="sxs-lookup"><span data-stu-id="0fe08-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="0fe08-108">**콘솔 응용 프로그램** 프로젝트를 새로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="0fe08-109">추가 `Imports` 문을 대 한 파일에는 `System.Linq.Expressions` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="0fe08-110">프로젝트에 `AndAlsoModifier` 클래스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
    ```vb  
    Public Class AndAlsoModifier  
        Inherits ExpressionVisitor  
  
        Public Function Modify(ByVal expr As Expression) As Expression  
            Return Visit(expr)  
        End Function  
  
        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression  
            If b.NodeType = ExpressionType.AndAlso Then  
                Dim left = Me.Visit(b.Left)  
                Dim right = Me.Visit(b.Right)  
  
                ' Make this binary expression an OrElse operation instead   
                ' of an AndAlso operation.  
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _  
                                             b.IsLiftedToNull, b.Method)  
            End If  
  
            Return MyBase.VisitBinary(b)  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="0fe08-111">이 클래스는 <xref:System.Linq.Expressions.ExpressionVisitor> 클래스를 상속하며, 조건부 `AND` 작업을 나타내는 식을 수정하도록 특수화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="0fe08-112">해당 작업을 조건부 `AND`에서 조건부 `OR`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="0fe08-113">조건부 `AND` 식은 이진 식으로 표현되기 때문에 이 작업을 위해 클래스는 기본 형식의 <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="0fe08-114">`VisitBinary` 메서드에서 전달된 식이 조건부 `AND` 작업을 나타내는 경우 코드는 조건부 `AND` 연산자 대신 조건부 `OR` 연산자가 포함된 새 식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="0fe08-115">`VisitBinary`에 전달된 식이 조건부 `AND` 작업을 나타내지 않는 경우 메서드는 기본 클래스 구현을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="0fe08-116">기본 클래스 메서드는 전달된 식 트리와 유사한 노드를 생성하지만 노드의 하위 트리가 방문자에 의해 재귀적으로 생성된 식 트리로 바뀌었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="0fe08-117">추가 `Imports` 문을 대 한 파일에는 `System.Linq.Expressions` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="0fe08-118">코드를 추가 하는 `Main` 메서드를 식 트리를 만들고는 메서드에 전달 하는 Module1.vb 파일의 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
    ```vb  
    Dim expr As Expression(Of Func(Of String, Boolean)) = _  
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")  
  
    Console.WriteLine(expr)  
  
    Dim modifier As New AndAlsoModifier()  
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))  
  
    Console.WriteLine(modifiedExpr)  
  
    ' This code produces the following output:  
    ' name => ((name.Length > 10) && name.StartsWith("G"))  
    ' name => ((name.Length > 10) || name.StartsWith("G"))  
    ```  
  
     <span data-ttu-id="0fe08-119">코드에서 조건부 `AND` 작업이 포함된 식을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="0fe08-120">그런 다음 `AndAlsoModifier` 클래스 인스턴스를 만들고 이 클래스의 `Modify` 메서드에 식을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="0fe08-121">원본 및 수정된 식 트리가 둘 다 출력되어 변경 내용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="0fe08-122">응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe08-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fe08-123">See Also</span></span>  
 [<span data-ttu-id="0fe08-124">방법: 식 트리 (Visual Basic)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe08-124">How to: Execute Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)  
 [<span data-ttu-id="0fe08-125">식 트리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fe08-125">Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
