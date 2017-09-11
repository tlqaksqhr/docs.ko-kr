---
title: "방법: 식 트리 (Visual Basic) 수정 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2f0d383cbac639212519177fb1825875682f6233
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="d5e7f-102">방법: 식 트리 (Visual Basic)를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="d5e7f-103">이 항목에서는 식 트리를 수정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="d5e7f-104">식 트리는 변경할 수 없기는 수정할 수 없음을 직접 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="d5e7f-105">식 트리를 변경 하려면 기존 식 트리의 복사본을 만들고 해당 복사본을 만들 때 필요한 사항을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="d5e7f-106">사용할 수는 <xref:System.Linq.Expressions.ExpressionVisitor>클래스 기존 식 트리를 이동 하 고 각 노드를 방문할 복사할.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="d5e7f-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="d5e7f-107">식 트리를 수정 하려면</span><span class="sxs-lookup"><span data-stu-id="d5e7f-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="d5e7f-108">새 **콘솔 응용 프로그램** 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="d5e7f-109">추가 `Imports` 문을 대 한 파일에는 `System.Linq.Expressions` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="d5e7f-110">추가 된 `AndAlsoModifier` 프로젝트에 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="d5e7f-111">이 클래스는 상속 된 <xref:System.Linq.Expressions.ExpressionVisitor>클래스 및 조건부를 나타내는 식을 수정 하도록 특수화 `AND` 작업.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="d5e7f-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="d5e7f-112">조건문에서 이러한 작업 변경 `AND` 는 조건부를 `OR`합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="d5e7f-113">이렇게 하려면 클래스 재정의 <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>기본 형식의 메서드 때문에 조건부 `AND` 식이 이진 식으로 표시 됩니다.</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A></span><span class="sxs-lookup"><span data-stu-id="d5e7f-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="d5e7f-114">에 `VisitBinary` 메서드를 전달 되는 식이 조건문을 나타내는 경우 `AND` 작업, 코드에서는 생성 된 조건부를 포함 하는 새 식을 `OR` 연산자 대신 조건부 `AND` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="d5e7f-115">경우에 전달 되는 식 `VisitBinary` 는 조건부를 나타내지 않습니다 `AND` 작업 메서드 기본 클래스 구현에 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="d5e7f-116">노드 같은, 전달 되는 식 트리를 생성 하지만 노드는 하위 트리가 식 트리를 대체 하 고 기본 클래스 메서드는 방문자가 반복적으로 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="d5e7f-117">추가 `Imports` 문을 대 한 파일에는 `System.Linq.Expressions` 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="d5e7f-118">코드를 추가 하는 `Main` 식 트리를 만들고이 메서드에 전달 하는 Module1.vb 파일의 메서드에서는 파일을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="d5e7f-119">코드는 조건부를 포함 하는 식을 만듭니다 `AND` 작업 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="d5e7f-120">인스턴스를 만든 후는 `AndAlsoModifier` 식을 전달 하 고 클래스는 `Modify` 이 클래스의 메서드.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="d5e7f-121">변경 내용을 표시 하는 원본 데이터베이스와 수정 된 식 트리 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="d5e7f-122">응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e7f-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e7f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5e7f-123">See Also</span></span>  
 <span data-ttu-id="d5e7f-124">[방법: 식 트리 (Visual Basic)를 실행 합니다.](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span><span class="sxs-lookup"><span data-stu-id="d5e7f-124">[How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span></span>  
<span data-ttu-id="d5e7f-125"> [식 트리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span><span class="sxs-lookup"><span data-stu-id="d5e7f-125"> [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
