---
title: "Function 프로시저(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Function 프로시저"
  - "반환 값, function 프로시저"
  - "Visual Basic 코드, 프로시저"
  - "프로시저, 호출"
  - "프로시저, Function 프로시저"
  - "구문, function 프로시저"
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Function 프로시저(Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Function` 프로시저는 `Function` 문과 `End Function` 문 사이에 포함된 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문입니다.  `Function` 프로시저는 작업을 수행한 다음 호출 코드에 제어를 반환합니다.  제어를 반환할 때 값도 함께 반환합니다.  
  
 프로시저가 호출될 때마다 `Function` 문 다음의 첫 실행 문에서 시작하여 첫 번째 `End Function`, `Exit Function` 또는 `Return` 문이 나타날 때까지 프로시저 문이 실행됩니다.  
  
 모듈, 클래스 또는 구조체에서 `Function` 프로시저를 정의할 수 있습니다.  프로시저는 기본적으로 `Public`입니다. 즉, 프로시저가 정의된 모듈, 클래스 또는 구조체에 액세스할 수 있는 응용 프로그램의 어느 곳에서나 해당 프로시저를 호출할 수 있습니다.  
  
 `Function` 프로시저는 호출 코드에 의해 자신에게 전달되는 상수, 변수, 식 등의 인수를 포함할 수 있습니다.  
  
## 선언 구문  
 `Function` 프로시저를 선언하는 구문은 다음과 같습니다.  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 *modifiers*는 오버로딩, 재정의, 공유 및 숨김에 대한 액세스 수준과 정보를 지정할 수 있습니다.  자세한 내용은 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)을 참조하십시오.  
  
 모든 매개 변수는 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)에서 선언하는 것과 똑같은 방식으로 선언합니다.  
  
### 데이터 형식  
 모든 `Function` 프로시저는 각 변수와 마찬가지로 특정 데이터 형식을 갖습니다.  이 데이터 형식은 `Function` 문에서 `As` 절로 지정되며 함수가 호출 코드에 반환하는 값의 데이터 형식을 결정합니다.  다음은 이에 대한 선언 샘플입니다.  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 자세한 내용은 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)의 "구성 요소"를 참조하십시오.  
  
## 반환 값  
 값은 `Function` 프로시저를 보냅니다 호출 코드에 반환 값 이라고 합니다.  프로시저는 다음과 같은 두 가지 방법으로 이 값을 반환합니다.  
  
-   이 프로시저는 `Return` 문을 사용하여 반환 값을 지정하고 호출 프로그램에 제어를 즉시 반환합니다.  다음은 이에 대한 예입니다.  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ' The following statement immediately transfers control back  
        ' to the calling code and returns the value of Expression.  
        Return Expression  
    End Function  
    ```  
  
-   프로시저의 하나 이상의 문에서 고유 함수 이름에 값을 할당합니다.  제어는 `Exit Function` 또는 `End Function` 문이 실행될 때까지 호출 프로그램에 반환되지 않습니다.  다음은 이에 대한 예입니다.  
  
    ```vb  
    Function FunctionName [(ParameterList)] As ReturnType  
        ‘ The following statement does not transfer control back to the calling code.  
        FunctionName = Expression  
        ' When control returns to the calling code, Expression is the return value.  
    End Function  
    ```  
  
 반환 값을 함수 이름에 할당하는 방식을 사용하면 프로그램이 `Exit Function`이나 `End Function` 문을 만나기 전까지 프로시저에서 제어를 반환하지 않는다는 장점이 있습니다.  따라서, 예비 값을 할당한 다음 필요에 따라 나중에 조정할 수 있습니다.  
  
 반환 값에 대 한 자세한 내용은 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).  배열을 반환 하는 방법에 대 한에 대 한 자세한 내용은 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## 호출 구문  
 할당문의 오른쪽이나 식에 프로시저 이름과 인수를 포함하여 `Function` 프로시저를 호출합니다.  선택적 인수를 제외한 모든 인수에 값을 지정하고 인수 목록을 괄호로 묶어야 합니다.  인수가 제공되지 않는 경우 괄호를 생략해도 됩니다.  
  
 `Function` 프로시저를 호출하는 구문은 다음과 같습니다.  
  
 *lvalue*  `=` *functionname* `[(` *argumentlist* `)]`  
  
 `If ((` *functionname* `[(` *argumentlist* `)] / 3) <=` *expression* `) Then`  
  
 `Function` 프로시저를 호출할 때 항상 반환 값을 사용할 필요는 없습니다.  반환 값을 사용하지 않으면 함수의 모든 동작이 수행되고 반환 값은 무시됩니다.  대개 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>를 이러한 방법으로 호출합니다.  
  
### 선언과 호출에 대한 설명  
 다음 `Function` 프로시저는 직각 삼각형의 두 변의 값을 사용하여 가장 긴 변\(빗변\)의 길이를 계산합니다.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/function-procedures_1.vb)]  
  
 다음 예제에서는 일반적인 `hypotenuse` 호출을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/function-procedures_2.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [How to: Create a Procedure that Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure-that-returns-a-value.md)   
 [How to: Return a Value from a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-return-a-value-from-a-procedure.md)   
 [How to: Call a Procedure That Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)