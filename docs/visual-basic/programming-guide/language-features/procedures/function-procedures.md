---
title: "Function 프로시저 (Visual Basic) | Microsoft 문서"
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
- Function procedures
- return values, function procedures
- Visual Basic code, procedures
- procedures, calling
- procedures, Function procedures
- syntax, function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 11baaa6985f0681aa9c67c4f2470fb9917db5b78
ms.lasthandoff: 03/13/2017

---
# <a name="function-procedures-visual-basic"></a>Function 프로시저(Visual Basic)
A `Function` 절차는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 로 묶인 명령문의 `Function` 및 `End Function` 문입니다. `Function` 프로시저는 작업을 수행한 다음 호출 코드에 제어를 반환 합니다. 제어를 반환 하기 호출 코드에도 값을 반환 합니다.  
  
 프로시저가 호출 된 문이 실행 될 때마다 시작 후 첫 번째 실행 문에 `Function` 문과 여 첫 번째 `End Function`, `Exit Function`, 또는 `Return` 문을 발견 했습니다.  
  
 정의할 수는 `Function` 모듈, 클래스 또는 구조체에는 프로시저입니다. `Public` 어디에서 나 호출할 수 있습니다 즉 기본적으로, 모듈, 클래스 또는 정의 된 구조에 액세스 권한이 있는 응용 프로그램에 있습니다.  
  
 A `Function` 프로시저와 같은 상수, 변수 또는 호출 코드에 의해 전달 되는 식을 인수를 사용할 수 있습니다.  
  
## <a name="declaration-syntax"></a>선언 구문  
 선언 구문은 `Function` 절차는 다음과 같습니다.  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *한정자* 오버 로드, 재정의 공유 및 숨김 관한 정보와 액세스 수준을 지정할 수 있습니다. 자세한 내용은 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
 에 대 한와 동일한 방식으로 각 매개 변수를 선언 [Sub 프로시저](./sub-procedures.md)합니다.  
  
### <a name="data-type"></a>데이터 형식  
 모든 `Function` 프로시저에는 데이터 형식, 각 변수와 마찬가지로 않습니다. 이 데이터 형식은 지정 되는 `As` 절에는 `Function` 하며 문, 함수 호출 코드로 반환 값의 데이터 형식을 결정 합니다. 다음 샘플 선언 이러한 경우를 설명 합니다.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 자세한 내용은 "부분"의 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.  
  
## <a name="returning-values"></a>값 반환  
 값을 `Function` 프로시저에서 전송 하는 호출 하는 코드를 다시 반환 값 이라고 합니다. 프로시저는 두 가지 방법 중 하나에서이 값을 반환합니다.  
  
-   사용 하 여는 `Return` 반환 값 및 반환을 지정 하는 문을 호출 프로그램에 즉시 제어 합니다. 다음은 이에 대한 예입니다.  
  
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
  
 함수 이름에는 반환 값을 할당의 장점은 만날 때까지 제어 프로시저에서 반환 되지 않는 한 `Exit Function` 또는 `End Function` 문입니다. 이 옵션을 사용 하면 예비 값을 할당 하 고 필요한 경우 나중에 조정할 수 있습니다.  
  
 값을 반환 하는 방법에 대 한 자세한 내용은 참조 [Function 문의](../../../../visual-basic/language-reference/statements/function-statement.md)합니다. 배열을 반환 하는 방법에 대 한 정보를 참조 하십시오. [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.  
  
## <a name="calling-syntax"></a>호출 구문  
 호출 하는 `Function` 이름과 대입문의 또는 식의 오른쪽에 인수를 포함 하 여 프로시저입니다. 선택적 인수가 아닌 모든 인수에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다. 없는 인수를 제공 하는 경우에 필요에 따라 괄호를 생략할 수 있습니다.  
  
 에 대 한 호출에 대 한 구문은 `Function` 절차는 다음과 같습니다.  
  
 *lvalue*`=`*functionname* `[(` *argumentlist*    `)]`  
  
 `If ((`*functionname* `[(` *argumentlist* `)] / 3) <=` *식*  `) Then`  
  
 호출 하는 경우는 `Function` 프로시저 않아도 해당 반환 값을 사용 하도록 합니다. 그렇지 않으면 함수는 모든 작업을 수행 하 고, 있지만 반환 값은 무시 됩니다. <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>이 방법으로 흔히 이라고 합니다.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
### <a name="illustration-of-declaration-and-call"></a>선언 및 호출의 그림  
 다음 `Function` 프로시저 가장 긴 면 또는 다른 두 가지 측면에 대 한 값이 제공 하는 직각 삼각형의 빗변을 계산 합니다.  
  
 [!code-vb[VbVbcnProcedures #&1;](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 다음 예제에서는 호출을 `hypotenuse`합니다.  
  
 [!code-vb[VbVbcnProcedures #&6;](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [속성 프로시저](./property-procedures.md)   
 [연산자 프로시저](./operator-procedures.md)   
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)   
 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [방법: 값을 반환 하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)   
 [방법: 프로시저에서 값을 반환 합니다.](./how-to-return-a-value-from-a-procedure.md)   
 [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
