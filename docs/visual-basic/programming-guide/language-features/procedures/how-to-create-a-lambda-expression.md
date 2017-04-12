---
title: "방법: 람다 식 (Visual Basic) 만들기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5e105e87b1e63218f2c3c2204350257c139b5837
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>방법: 람다 식 만들기(Visual Basic)
A *람다 식을* 은 함수 또는 서브루틴에 이름이 없습니다입니다. 람다 식은 대리자 형식이 유효한 모든 곳에서 사용할 수 있습니다.  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>한 줄 람다 식 함수를 만들려면  
  
1.  대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Function`다음 예제와 같이 합니다.  
  
     `Dim add1 =`   `Function`  
  
2.  괄호로 직후 `Function`를 함수 매개 변수를 입력 합니다. 뒤에 이름을 지정 하지 않으면 `Function`합니다.  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3.  매개 변수 목록 다음 단일 식 함수 본문으로 입력 합니다. 식이 계산 되는 값에는 함수에서 반환한 값이입니다. 사용 하지 않는 한 `As` 절을 반환 형식을 지정 합니다.  
  
     [!code-vb[VbVbalrLambdas #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_1.vb)]  
  
     정수 인수를 전달 하 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas #&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_2.vb)]  
  
4.  또는 동일한 결과 다음 예제에서 수행 됩니다.  
  
     [!code-vb[VbVbalrLambdas #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_3.vb)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>한 줄 람다 식 서브루틴을 만들려면  
  
1.  대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Sub`다음 예제와 같이 합니다.  
  
     `Dim add1 =`   `Sub`  
  
2.  괄호로 직후 `Sub`, 서브루틴의 매개 변수를 입력 합니다. 뒤에 이름을 지정 하지 않으면 `Sub`합니다.  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3.  매개 변수 목록 다음 단일 문을 서브루틴의 본문으로 입력 합니다.  
  
     [!code-vb[VbVbalrLambdas #&17;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_4.vb)]  
  
     문자열 인수를 전달 하 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas #&18;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_5.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>여러 줄 람다 식 함수를 만들려면  
  
1.  대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Function`다음 예제와 같이 합니다.  
  
     `Dim add1 =`   `Function`  
  
2.  괄호로 직후 `Function`를 함수 매개 변수를 입력 합니다. 뒤에 이름을 지정 하지 않으면 `Function`합니다.  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3.  Enter 키를 누릅니다. `End Function` 문이 자동으로 추가 됩니다.  
  
4.  함수 본문 내에서 식을 만들고 값을 반환 하는 다음 코드를 추가 합니다. 사용 하지 않는 한 `As` 절을 반환 형식을 지정 합니다.  
  
     [!code-vb[VbVbalrLambdas #&19;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_6.vb)]  
  
     정수 인수를 전달 하 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas #&20;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_7.vb)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>여러 줄 람다 식 서브루틴을 만들려면  
  
1.  대리자 형식을 사용할 수 있는 모든 상황에서 키워드를 입력 `Sub`다음 예제와 같이 합니다.  
  
     `Dim add1 =`   `Sub`  
  
2.  괄호로 직후 `Sub`, 서브루틴의 매개 변수를 입력 합니다. 뒤에 이름을 지정 하지 않으면 `Sub`합니다.  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3.  Enter 키를 누릅니다. `End Sub` 문이 자동으로 추가 됩니다.  
  
4.  함수 본문 내에서 서브루틴 호출 될 때 실행 하는 다음 코드를 추가 합니다.  
  
     [!code-vb[VbVbalrLambdas #&21;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_8.vb)]  
  
     문자열 인수를 전달 하 람다 식을 호출 합니다.  
  
     [!code-vb[VbVbalrLambdas #&22;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_9.vb)]  
  
## <a name="example"></a>예제  
 람다 식의 일반적인 사용 되는 형식의 매개 변수에 대해 인수로 전달 될 수 있는 함수를 정의 하는 `Delegate`합니다. 다음 예제에서는 <xref:System.Diagnostics.Process.GetProcesses%2A>메서드는 로컬 컴퓨터에서 실행 중인 프로세스의 배열을 반환 합니다.</xref:System.Diagnostics.Process.GetProcesses%2A> <xref:System.Linq.Enumerable.Where%2A>메서드에서 <xref:System.Linq.Enumerable>클래스 필요는 `Boolean` 인수로 위임.</xref:System.Linq.Enumerable> </xref:System.Linq.Enumerable.Where%2A> 예에서 람다 식이 해당 용도로 사용 됩니다. 반환 `True` 각 프로세스에 대 한 스레드 한 개만 있으며에서 선택 됩니다 `filteredList`합니다.  
  
 [!code-vb[VbVbalrLambdas #&10;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_10.vb)]  
  
 앞의 예제는 작성 된 다음 코드와 동일한 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 구문:  
  
 [!code-vb[VbVbalrLambdas #&11;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-create-a-lambda-expression_11.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [람다 식](./lambda-expressions.md)   
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [방법: 프로시저에 Visual Basic에서 다른 프로시저 전달](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Visual Basic의 LINQ 소개](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
