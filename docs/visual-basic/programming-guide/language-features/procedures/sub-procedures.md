---
title: "Sub Procedures (Visual Basic) | Microsoft Docs"
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
  - "Sub procedures, about Sub procedures"
  - "statement blocks"
  - "Sub procedures, calling"
  - "procedures, calling"
  - "Sub procedures, syntax"
  - "Sub procedures"
  - "procedures, Sub"
  - "syntax, Sub procedures"
ms.assetid: 6a0a4958-ed0a-4d3d-8d31-0772c82bda58
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Sub Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Sub` 프로시저는 `Sub` 문과 `End Sub` 문 사이에 포함된 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문입니다.  `Sub` 프로시저는 작업을 수행한 다음 호출 코드로 제어를 반환하지만 호출 코드에 값을 반환하지는 않습니다.  
  
 프로시저가 호출될 때마다 `Sub` 문 다음의 첫 실행 문에서 시작하여 `End Sub`, `Exit Sub` 또는 `Return` 문이 처음 나타날 때까지 해당 문이 실행됩니다.  
  
 `Sub` 프로시저는 모듈, 클래스 및 구조체에서 정의할 수 있습니다.  이 프로시저는 기본적으로 `Public`이므로 프로시저를 정의한 해당 모듈, 클래스 또는 구조체에 액세스할 수 있는 응용 프로그램의 모든 위치에서 호출할 수 있습니다.  *메서드*라는 용어는 정의하는 모듈, 클래스 또는 구조체 외부에서 액세스되는 `Sub` 또는 `Function` 프로시저를 나타냅니다.  자세한 내용은 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)을 참조하십시오.  
  
 `Sub` 프로시저는 호출 코드를 통해 전달되는 상수, 변수, 식 등의 인수를 사용할 수 있습니다.  
  
## 선언 구문  
 `Sub` 프로시저를 선언하는 구문은 다음과 같습니다.  
  
 `[` *modifiers* `] Sub`  *subname* `[(` *parameterlist* `)]`  
  
 `' Statements of the Sub procedure.`  
  
 `End Sub`  
  
 `modifiers`는 오버로딩, 재정의, 공유 및 숨김에 대한 액세스 수준과 정보를 지정할 수 있습니다.  자세한 내용은 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)을 참조하십시오.  
  
## 매개 변수 선언  
 변수를 선언하는 방법과 마찬가지로 각 프로시저 매개 변수를 선언하여 매개 변수 이름과 데이터 형식을 지정할 수 있습니다.  또한 전달 메커니즘을 지정하고 매개 변수가 선택적 요소인지, 매개 변수 배열인지도 지정할 수 있습니다.  
  
 매개 변수 목록의 각 매개 변수에 대한 구문은 다음과 같습니다.  
  
 `[Optional] [ByVal | ByRef] [ParamArray]`  *parametername*  `As`  *datatype*  
  
 매개 변수가 선택적 요소이면 매개 변수를 선언할 때 기본값도 지정해야 합니다.  기본값을 지정하는 구문은 다음과 같습니다.  
  
 `Optional [ByVal | ByRef]`  *parametername*  `As`  *datatype*  `=`  *defaultvalue*  
  
### 매개 변수를 지역 변수로 처리  
 프로시저로 제어가 전달되면 각 매개 변수는 지역 변수로 처리됩니다.  즉, 매개 변수의 수명이 프로시저의 수명과 같아지고, 매개 변수 범위는 전체 프로시저가 됩니다.  
  
## 호출 구문  
 독립 실행형 호출 문을 사용하여 `Sub` 프로시저를 명시적으로 호출합니다.  식에서 프로시저 이름을 사용하여 프로시저를 호출할 수는 없습니다.  선택적 인수를 제외한 모든 인수에 값을 지정하고 인수 목록을 괄호로 묶어야 합니다.  인수가 제공되지 않는 경우 괄호를 생략해도 됩니다.  `Call` 키워드는 선택적 요소이지만 사용하지 않는 것이 좋습니다.  
  
 `Sub` 프로시저를 호출하는 구문은 다음과 같습니다.  
  
 `[Call]`  *subname* `[(` *argumentlist* `)]`  
  
 메서드를 정의하는 클래스 외부에서 `Sub` 메서드를 호출할 수 있습니다.  우선 `New` 키워드를 사용하여 클래스의 인스턴스를 만들거나 클래스의 인스턴스를 반환하는 메서드를 호출해야 합니다.  자세한 내용은 [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md)를 참조하십시오.  그런 다음 아래 구문을 사용하여 인스턴스 개체의 `Sub` 메서드를 사용할 수 있습니다.  
  
 *Object*.*methodname*`[(`*argumentlist*`)]`  
  
### 선언과 호출에 대한 설명  
 다음 `Sub` 프로시저는 응용 프로그램에서 수행하려는 작업을 컴퓨터 사용자에게 알려 주고 타임스탬프도 표시합니다.  이 코드를 모든 작업의 시작 부분에 복제하는 대신 응용 프로그램의 여러 위치에서 `tellOperator`를 호출합니다.  각 호출은 막 시작하려는 작업을 식별하는  `task`  인수의 문자열을 전달합니다.  
  
 [!code-vb[VbVbcnProcedures#2](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/sub-procedures_1.vb)]  
  
 다음 예제에서는 일반적인 `tellOperator` 호출을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#3](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/sub-procedures_2.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Property 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [How to: Call a Procedure that Does Not Return a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)   
 [How to: Call an Event Handler in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-event-handler.md)