---
title: Function 프로시저(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad4f55a9dd9fbd68c36dd53a01f97ddb03c2bb9b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="function-procedures-visual-basic"></a>Function 프로시저(Visual Basic)
A `Function` 절차는 일련의 Visual Basic 문으로 둘러싸인는 `Function` 및 `End Function` 문. `Function` 프로시저는 작업을 수행한 다음 호출 코드에 제어를 반환 합니다. 제어를 반환 하기 호출 코드에도 값을 반환 합니다.  
  
 다음의 첫 번째 실행 문에서로 프로시저가 호출 된 문이 실행 될 때마다 시작는 `Function` 문과 여 첫 번째 `End Function`, `Exit Function`, 또는 `Return` 문을 발견 했습니다.  
  
 정의할 수는 `Function` 모듈, 클래스 또는 구조체의 절차입니다. `Public` 어디에서 나 호출할 수 즉 기본적으로 모듈, 클래스 또는 정의 된 구조체에 액세스 권한이 있는 응용 프로그램에서 합니다.  
  
 A `Function` 프로시저 상수, 변수 또는 호출 코드에 의해 전달 된 식 등의 인수를 사용할 수 있습니다.  
  
## <a name="declaration-syntax"></a>선언 구문  
 선언 구문이 `Function` 절차는 다음과 같습니다.  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *한정자* 오버 로드, 재정의 공유 및 숨김 관한 정보와 액세스 수준을 지정할 수 있습니다. 자세한 내용은 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
 에 대 한 작업을 수행한 동일한 방식으로 각 매개 변수를 선언 [Sub 프로시저](./sub-procedures.md)합니다.  
  
### <a name="data-type"></a>데이터 형식  
 모든 `Function` 프로시저에는 데이터 형식, 각 변수와 마찬가지로 않습니다. 이 데이터 형식은 지정 되는 `As` 절에는 `Function` 문 및 함수 호출 코드에 반환 하는 값의 데이터 형식을 결정 합니다. 다음 샘플 선언 이러한 경우를 설명 합니다.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 자세한 내용은의 "부분" 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
## <a name="returning-values"></a>값 반환  
 값을 `Function` 프로시저에서 전송 하는 호출 코드에 다시 반환 값에 호출 됩니다. 프로시저는 두 가지 방법 중 하나에서이 값을 반환합니다.  
  
-   사용 하 여는 `Return` 반환와 반환 값을 지정 하는 문을 호출 프로그램에 즉시 제어 합니다. 다음은 이에 대한 예입니다.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
-   프로시저의 하나 이상의 문에서 함수 이름에 값을 할당 합니다. 제어 될 때까지 호출 프로그램에 반환 하지 않는 한 `Exit Function` 또는 `End Function` 문이 실행 됩니다. 다음은 이에 대한 예입니다.  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 함수 이름에 반환 값을 할당의 장점은입니다에 도달할 때까지 제어 프로시저에서 반환 하지 않는 한 `Exit Function` 또는 `End Function` 문. 이 예비 값을 할당 하 고 필요 하면 나중에 조정 수 있습니다.  
  
 값을 반환 하는 방법에 대 한 자세한 내용은 참조 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다. 배열을 반환 하는 방법에 대 한 정보를 참조 하십시오. [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
## <a name="calling-syntax"></a>호출 구문  
 호출 된 `Function` 프로시저 이름 및 인수는 식 또는 대입문의 오른쪽을 포함 하 여 합니다. 모든 인수는 옵션에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다. 인수를 제공 하는 경우 괄호를 선택적으로 생략할 수 있습니다.  
  
 에 대 한 호출에 대 한 구문은 `Function` 절차는 다음과 같습니다.  
  
 *lvalue*`=`*functionname* `[(` *argumentlist*  `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=` *식*  `) Then`  
  
 호출 하는 경우는 `Function` 프로시저 않아도 해당 반환 값을 사용 하도록 합니다. 이렇게 하지 않으면 함수는 모든 작업이 수행 되었는지, 있지만 반환 값은 무시 됩니다. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 이런이 방식으로 라고도 합니다.  
  
### <a name="illustration-of-declaration-and-call"></a>선언 및 호출의 그림  
 다음 `Function` 프로시저 가장 긴 면 또는 다른 두 변에 대 한 값을 지정 하는 직각 삼각형의 빗변을 계산 합니다.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 다음 예제에서는 호출을 `hypotenuse`합니다.  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [방법: 값을 반환하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)  
 [방법: 프로시저에서 값 반환](./how-to-return-a-value-from-a-procedure.md)  
 [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
