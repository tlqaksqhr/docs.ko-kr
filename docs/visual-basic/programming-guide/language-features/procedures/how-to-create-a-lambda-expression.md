---
title: "How to: Create a Lambda Expression (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "lambda expressions [Visual Basic]"
  - "expressions [Visual Basic], lambda"
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Lambda Expression (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*람다 식*은 이름이 없는 함수 또는 서브루틴입니다.  대리자 형식이 유효한 모든 곳에서 람다 식을 사용할 수 있습니다.  
  
### 한 줄로 된 람다 식 함수를 만들려면  
  
1.  대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Function` 키워드를 입력합니다.  
  
     `Dim add1 =`   `Function`  
  
2.  `Function` 바로 뒤에 있는 괄호 안에 함수의 매개 변수를 입력합니다.  `Function` 뒤에는 이름을 지정하지 않습니다.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  매개 변수 목록 다음에 단일 식을 함수의 본문으로 입력합니다.  식에서 계산하는 값은 함수에서 반환된 값입니다.  `As` 절을 사용하여 반환 데이터 형식을 지정하지 마십시오.  
  
     [!code-vb[VbVbalrLambdas#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     정수 인수를 전달하여 람다 식을 호출합니다.  
  
     [!code-vb[VbVbalrLambdas#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  또는 다음 예제에 의해 같은 결과가 나올 수 있습니다.  
  
     [!code-vb[VbVbalrLambdas#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### 한 줄로 된 람다 식 서브루틴을 만들려면  
  
1.  대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Sub` 키워드를 입력합니다.  
  
     `Dim add1 =`   `Sub`  
  
2.  `Sub` 바로 뒤에 있는 괄호 안에 서브루틴의 매개 변수를 입력합니다.  `Sub` 뒤에는 이름을 지정하지 않습니다.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  매개 변수 목록 다음에 단일 문을 서브루틴의 본문으로 입력합니다.  
  
     [!code-vb[VbVbalrLambdas#17](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     문자열 인수를 전달하여 람다 식을 호출합니다.  
  
     [!code-vb[VbVbalrLambdas#18](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### 여러 줄로 된 람다 식 함수를 만들려면  
  
1.  대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Function` 키워드를 입력합니다.  
  
     `Dim add1 =`   `Function`  
  
2.  `Function` 바로 뒤에 있는 괄호 안에 함수의 매개 변수를 입력합니다.  `Function` 뒤에는 이름을 지정하지 않습니다.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Enter 키를 누릅니다.  `End Function` 문이 자동으로 추가됩니다.  
  
4.  함수 본문 내에 식을 만들고 값을 반환할 다음 코드를 추가합니다.  `As` 절을 사용하여 반환 데이터 형식을 지정하지 마십시오.  
  
     [!code-vb[VbVbalrLambdas#19](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     정수 인수를 전달하여 람다 식을 호출합니다.  
  
     [!code-vb[VbVbalrLambdas#20](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### 여러 줄로 된 람다 식 서브루틴을 만들려면  
  
1.  대리자 형식을 사용할 수 있는 경우 다음 예제와 같이 `Sub` 키워드를 입력합니다.  
  
     `Dim add1 =`   `Sub`  
  
2.  `Sub` 바로 뒤에 있는 괄호 안에 서브루틴의 매개 변수를 입력합니다.  `Sub` 뒤에는 이름을 지정하지 않습니다.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Enter 키를 누릅니다.  `End Sub` 문이 자동으로 추가됩니다.  
  
4.  함수 본문 내에 서브루틴 호출 시 실행할 다음 코드를 추가합니다.  
  
     [!code-vb[VbVbalrLambdas#21](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     문자열 인수를 전달하여 람다 식을 호출합니다.  
  
     [!code-vb[VbVbalrLambdas#22](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## 예제  
 람다 식의 일반적인 사용은 형식이 `Delegate`인 매개 변수에 대해 인수로 전달될 수 있는 함수를 정의하는 것입니다.  다음 예제에서 <xref:System.Diagnostics.Process.GetProcesses%2A> 메서드는 로컬 컴퓨터에서 실행되는 프로세스의 배열을 반환합니다.  <xref:System.Linq.Enumerable> 클래스의 <xref:System.Linq.Enumerable.Where%2A> 메서드에는 `Boolean` 대리자가 인수로 필요합니다.  이 예제의 람다 식이 해당 용도로 사용됩니다.  하나의 스레드만 있는 각 프로세스에 대해 `True`를 반환하고 `filteredList`에서 선택됩니다.  
  
 [!code-vb[VbVbalrLambdas#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 앞의 예제는 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 구문으로 작성된 다음 코드와 동일합니다.  
  
 [!code-vb[VbVbalrLambdas#11](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## 참고 항목  
 <xref:System.Linq.Enumerable>   
 [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)