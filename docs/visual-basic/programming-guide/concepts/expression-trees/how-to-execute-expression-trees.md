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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e12c45b417310f097d597561b2652ee793a4b2c0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a>방법: 식 트리 (Visual Basic)를 실행 합니다.
이 항목에서는 식 트리를 실행 하는 방법을 보여 줍니다. 값을 반환할 수는 식 트리 실행 또는 메서드를 호출 하는 등의 작업을 수행할 것 수 있습니다.  
  
 람다 식을 나타내는 식 트리만 실행할 수 있습니다. 형식이 <xref:System.Linq.Expressions.LambdaExpression>나 <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression> 람다 식을 나타내는 식 트리는 이러한 식 트리를 실행 하려면 호출의 <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>메서드를 실행 가능한 대리자로 만들고 대리자를 호출 합니다.</xref:System.Linq.Expressions.LambdaExpression.Compile%2A>  
  
> [!NOTE]
>  대리자의 형식, 알 수 없는 경우 즉, 람다 식 형식입니다 <xref:System.Linq.Expressions.LambdaExpression>아닌 <xref:System.Linq.Expressions.Expression%601>를 호출 해야는 <xref:System.Delegate.DynamicInvoke%2A>메서드를 직접 호출 하는 대신 대리자.</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression>  
  
 식 트리에 람다 식을 아닙니다 하는 경우에를 본문으로 호출 하 여 원래 식 트리를 가진 새 람다 식을 만들 수는 <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>메서드.</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> 그런 다음이 섹션의 앞부분에서 설명한 대로 람다 식을 실행할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 람다 식을 만들고 실행 하 여 숫자의 거듭제곱을 나타내는 식 트리를 실행 하는 방법을 보여 줍니다. 거듭제곱 수 만큼 거듭제곱을 나타내는 결과가 표시 됩니다.  
  
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
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   아직 참조 하지 않는 경우 System.Core.dll에 대 한 프로젝트 참조를 추가 합니다.  
  
-   System.Linq.Expressions 네임 스페이스를 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [식 트리 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [방법: 식 트리 (Visual Basic)를 수정 합니다.](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
