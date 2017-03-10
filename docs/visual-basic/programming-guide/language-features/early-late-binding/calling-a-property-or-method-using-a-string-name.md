---
title: "Calling a Property or Method Using a String Name (Visual Basic) | Microsoft Docs"
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
  - "passing operators"
  - "strings [Visual Basic], passing new operators as"
  - "objects [Visual Basic], setting properties"
  - "setting properties, object properties at run time"
  - "method calls, strings"
  - "methods [Visual Basic], calling with string names"
  - "calling methods, string names"
  - "properties [Visual Basic], setting at run time"
  - "CallByName function"
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Calling a Property or Method Using a String Name (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

대부분의 경우 디자인 타임에서 개체의 속성과 메서드를 찾을 수 있으며 코드를 작성하여 이를 처리할 수 있습니다.  그러나 개체의 속성과 메서드를 미리 알 수 없거나 최종 사용자에게 런타임에서 속성을 지정하거나 메서드를 실행할 수 있는 융통성을 제공하려는 경우도 있습니다.  
  
## CallByName 함수  
 예를 들어, 연산자를 COM 구성 요소로 전달하여 사용자가 입력한 식을 계산하는 클라이언트 응용 프로그램의 경우,  새 연산자를 필요로 하는 구성 요소에 계속 새 함수를 추가하고 있다고 가정합니다.  표준 개체 액세스 기술을 사용할 때 클라이언트 응용 프로그램이 새 연산자를 사용하려면 이를 다시 컴파일하고 다시 배포해야 합니다.  그러나 `CallByName` 함수를 사용하여 새 연산자를 문자열로 전달하면 응용 프로그램을 변경하지 않고 이러한 작업을 수행할 수 있습니다.  
  
 `CallByName` 함수를 사용하면 런타임에 문자열을 사용하여 속성이나 메서드를 지정할 수 있습니다.  `CallByName` 함수의 시그니처는 다음과 유사합니다.  
  
 *Result* \= `CallByName`\(*Object*, *ProcedureName*, *CallType*, *Arguments*\(\)\)  
  
 첫 번째 인수인 *Object*는 실행할 개체의 이름입니다.  *ProcedureName* 인수는 호출할 메서드나 속성 프로시저의 이름이 포함된 문자열을 사용합니다.  *CallType* 인수는 메서드\(`Microsoft.VisualBasic.CallType.Method`\), 속성 읽기\(`Microsoft.VisualBasic.CallType.Get`\) 또는 속성 설정\(`Microsoft.VisualBasic.CallType.Set`\) 등의 호출할 프로시저 유형을 나타내는 상수를 사용합니다.  선택적 요소인 *Arguments* 인수는 프로시저에 대한 모든 인수가 들어 있는 `Object` 형식의 배열을 사용합니다.  
  
 현재 솔루션의 클래스에 `CallByName`을 사용할 수도 있지만 일반적으로 이 함수는 COM 개체 또는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] 어셈블리의 개체에 액세스하는 데 사용됩니다.  
  
 `SquareRoot`라는 새 함수를 가지는 `MathClass` 클래스를 포함하는 어셈블리에 대한 참조를 추가한다고 가정합니다.  
  
 [!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#53)]  
  
 응용 프로그램에서 텍스트 상자 컨트롤을 사용하여 호출되는 메서드 및 해당 인수를 제어할 수 있습니다.  예를 들어, `TextBox1`에 계산할 식이 있고 `TextBox2`는 함수의 이름이 들어갈 입력란인 경우 다음 코드를 사용하여 `TextBox1`의 식에서 `SquareRoot` 함수를 호출할 수 있습니다.  
  
 [!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/visualbasic/VbVbalrOOP/OOP.vb#54)]  
  
 `TextBox1`에 "64"를 입력하고 `TextBox2`에 "SquareRoot"를 입력한 다음 `CallMath` 프로시저를 호출하면 `TextBox1`에 있는 숫자의 제곱근이 계산됩니다.  예제의 코드는 계산할 식이 포함된 문자열을 필수 인수로 사용하는 `SquareRoot` 함수를 호출하고 `TextBox1`에서 64의 제곱근인 "8"을 반환합니다.  물론 사용자가 `TextBox2`에 잘못된 값을 입력하거나 문자열에 메서드 이름 대신 속성 이름이 포함되어 있거나 메서드가 추가적인 필수 인수를 가지고 있으면 런타임 오류가 발생합니다.  `CallByName`을 사용할 때 이러한 오류나 기타 오류가 발생할 것으로 예상되면 오류 처리 코드를 추가해야 합니다.  
  
> [!NOTE]
>  `CallByName` 함수는 일부 경우에는 유용할 수 있지만 `CallByName`을 사용하여 프로시저를 호출하면 런타임에 바인딩된 호출보다 실행 속도가 약간 느리므로 성능 대비 유용성을 고려할 필요가 있습니다.  루프 내부에서처럼 반복적으로 호출되는 함수를 실행하면 `CallByName`이 성능에 심각한 영향을 줄 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>   
 [Determining Object Type](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)