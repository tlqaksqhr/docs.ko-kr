---
title: "방법: 식 트리 (Visual Basic)를 실행 합니다. | Microsoft 문서"
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
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
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
ms.openlocfilehash: 4cc2c9890c1f5efbc4036d94eef1adb05094ae40
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a><span data-ttu-id="ee0ca-102">방법: 식 트리 (Visual Basic)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-102">How to: Execute Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="ee0ca-103">이 항목에서는 식 트리를 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-103">This topic shows you how to execute an expression tree.</span></span> <span data-ttu-id="ee0ca-104">값을 반환할 수는 식 트리 실행 또는 메서드를 호출 하는 등의 작업을 수행할 것 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-104">Executing an expression tree may return a value, or it may just perform an action such as calling a method.</span></span>  
  
 <span data-ttu-id="ee0ca-105">람다 식을 나타내는 식 트리만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-105">Only expression trees that represent lambda expressions can be executed.</span></span> <span data-ttu-id="ee0ca-106">형식이 <xref:System.Linq.Expressions.LambdaExpression>나 <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression> 람다 식을 나타내는 식 트리는</span><span class="sxs-lookup"><span data-stu-id="ee0ca-106">Expression trees that represent lambda expressions are of type <xref:System.Linq.Expressions.LambdaExpression> or <xref:System.Linq.Expressions.Expression%601>.</span></span> <span data-ttu-id="ee0ca-107">이러한 식 트리를 실행 하려면 호출의 <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>메서드를 실행 가능한 대리자로 만들고 대리자를 호출 합니다.</xref:System.Linq.Expressions.LambdaExpression.Compile%2A></span><span class="sxs-lookup"><span data-stu-id="ee0ca-107">To execute these expression trees, call the <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> method to create an executable delegate, and then invoke the delegate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ee0ca-108">대리자의 형식, 알 수 없는 경우 즉, 람다 식 형식입니다 <xref:System.Linq.Expressions.LambdaExpression>아닌 <xref:System.Linq.Expressions.Expression%601>를 호출 해야는 <xref:System.Delegate.DynamicInvoke%2A>메서드를 직접 호출 하는 대신 대리자.</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression></span><span class="sxs-lookup"><span data-stu-id="ee0ca-108">If the type of the delegate is not known, that is, the lambda expression is of type <xref:System.Linq.Expressions.LambdaExpression> and not <xref:System.Linq.Expressions.Expression%601>, you must call the <xref:System.Delegate.DynamicInvoke%2A> method on the delegate instead of invoking it directly.</span></span>  
  
 <span data-ttu-id="ee0ca-109">식 트리에 람다 식을 아닙니다 하는 경우에를 본문으로 호출 하 여 원래 식 트리를 가진 새 람다 식을 만들 수는 <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>메서드.</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29></span><span class="sxs-lookup"><span data-stu-id="ee0ca-109">If an expression tree does not represent a lambda expression, you can create a new lambda expression that has the original expression tree as its body, by calling the <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> method.</span></span> <span data-ttu-id="ee0ca-110">그런 다음이 섹션의 앞부분에서 설명한 대로 람다 식을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-110">Then, you can execute the lambda expression as described earlier in this section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee0ca-111">예제</span><span class="sxs-lookup"><span data-stu-id="ee0ca-111">Example</span></span>  
 <span data-ttu-id="ee0ca-112">다음 코드 예제에서는 람다 식을 만들고 실행 하 여 숫자의 거듭제곱을 나타내는 식 트리를 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-112">The following code example demonstrates how to execute an expression tree that represents raising a number to a power by creating a lambda expression and executing it.</span></span> <span data-ttu-id="ee0ca-113">거듭제곱 수 만큼 거듭제곱을 나타내는 결과가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-113">The result, which represents the number raised to the power, is displayed.</span></span>  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ee0ca-114">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ee0ca-114">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ee0ca-115">아직 참조 하지 않는 경우 System.Core.dll에 대 한 프로젝트 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-115">Add a project reference to System.Core.dll if it is not already referenced.</span></span>  
  
-   <span data-ttu-id="ee0ca-116">System.Linq.Expressions 네임 스페이스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee0ca-116">Include the System.Linq.Expressions namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee0ca-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee0ca-117">See Also</span></span>  
 <span data-ttu-id="ee0ca-118">[식 트리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span><span class="sxs-lookup"><span data-stu-id="ee0ca-118">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) </span></span>  
<span data-ttu-id="ee0ca-119"> [방법: 식 트리 (Visual Basic)를 수정 합니다.](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span><span class="sxs-lookup"><span data-stu-id="ee0ca-119"> [How to: Modify Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)</span></span>
