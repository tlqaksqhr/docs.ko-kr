---
title: "Property 프로시저(Visual Basic) | Microsoft Docs"
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
  - "Set 문, Property 프로시저"
  - "Visual Basic 코드, 프로시저"
  - "반환 값, Property 프로시저"
  - "구문, Property 프로시저"
  - "프로시저, property"
  - "Visual Basic 코드, 속성"
  - "프로시저, 호출"
  - "속성[Visual Basic], 사용자 지정"
  - "Property 프로시저"
  - "Get 문, property 프로시저"
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Property 프로시저(Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

속성 프로시저는 모듈, 클래스 또는 구조체에서 사용자 지정 속성을 조작하는 일련의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문입니다.  속성 프로시저를 *속성 접근자*라고도 합니다  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에는 다음과 같은 속성 프로시저가 있습니다.  
  
-   `Get` 프로시저는 속성 값을 반환합니다.  식에서 속성에 액세스할 때 호출됩니다.  
  
-   `Set` 프로시저는 개체 참조를 포함하여 속성 값을 설정합니다.  속성에 값을 할당할 때 호출됩니다.  
  
 일반적으로 `Get` 문과 `Set` 문을 사용하여 속성 프로시저를 쌍으로 정의할 수 있지만, 속성이 읽기 전용\([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)\)이거나 쓰기 전용\([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)\)일 경우 두 프로시저 중 하나만 정의할 수 있습니다.  
  
 자동 구현된 속성을 사용할 때 `Get` 및 `Set` 프로시저를 생략할 수 있습니다.  자세한 내용은 [Auto\-Implemented Properties](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하십시오.  
  
 클래스, 구조체 및 모듈에서 속성을 정의할 수 있습니다.  속성은 기본적으로 `Public`입니다. 즉, 속성 컨테이너에 액세스할 수 있는 응용 프로그램의 어느 곳에서나 이 컨테이너에 포함된 속성을 호출할 수 있습니다.  
  
 속성과 변수를 비교한 내용을 보려면 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)을 참조하십시오.  
  
## 선언 구문  
 속성 자체는 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) 문과 `End Property` 문 사이에 포함된 코드 블록으로 정의됩니다.  이 블록 안에서 각 속성 프로시저는 선언문\(`Get` 또는 `Set`\)과 짝이 되는 `End` 선언 사이에 포함된 내부 블록으로 나타납니다.  
  
 속성 및 해당 프로시저를 선언하는 구문은 다음과 같습니다.  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 `Modifiers`는 속성이 읽기 전용인지, 쓰기 전용인지 외에도 오버로딩, 재정의, 공유 및 숨김에 관한 정보와 액세스 수준을 지정할 수 있습니다.  `AccessLevel` 에 있는 `Get` 또는 `Set` 프로시저 속성에 지정 된 액세스 수준 보다 제한적인 수준이 될 수 있습니다.  자세한 내용은 [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md)을 참조하십시오.  
  
### 데이터 형식  
 속성의 데이터 형식과 보안 주체 액세스 수준은 속성 프로시저가 아니라 `Property` 문으로 정의됩니다.  속성은 한 가지 데이터 형식만 가질 수 있습니다.  예를 들어, `Decimal` 값을 저장하고 `Double` 값을 가져오도록 속성을 정의할 수 없습니다.  
  
### 액세스 수준  
 그러나 속성에 대한 보안 주체 액세스 수준을 정의하고 해당 속성 프로시저 중 하나에서 액세스 수준을 더욱 제한할 수 있습니다.  예를 들어, `Public` 속성을 정의한 다음 `Private Set` 프로시저를 정의할 수 있습니다.  `Get` 프로시저는 `Public`으로 유지됩니다.  속성 프로시저 중 하나에서만 액세스 수준을 변경할 수 있으며 해당 액세스 수준을 보안 주체 액세스 수준보다 제한적으로만 설정할 수 있습니다.  자세한 내용은 [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md)을 참조하십시오.  
  
## 매개 변수 선언  
 모든 매개 변수는 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)에서 선언하는 것과 똑같은 방식으로 선언합니다. 단, 전달 메커니즘은 `ByVal`이어야 합니다.  
  
 매개 변수 목록의 각 매개 변수에 대한 구문은 다음과 같습니다.  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 매개 변수가 선택적 요소이면 매개 변수를 선언할 때 기본값도 지정해야 합니다.  기본값을 지정하는 구문은 다음과 같습니다.  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## 속성 값  
 `Get` 프로시저에서는 호출 식에 속성 값으로 값이 반환됩니다.  
  
 `Set` 프로시저에서는 새 속성 값이 `Set` 문의 매개 변수로 전달됩니다.  매개 변수를 명시적으로 선언할 때는 속성과 동일한 데이터 형식으로 선언해야 합니다.  매개 변수를 선언하지 않으면 컴파일러에서 암시적 매개 변수 `Value`를 사용하여 속성에 새 값을 할당합니다.  
  
## 호출 구문  
 속성을 참조하여 속성 프로시저를 암시적으로 호출합니다.  선택적 인수를 제외한 모든 인수에 값을 지정하고 인수 목록을 괄호로 묶어야 하는 것 외에는 변수 이름을 사용하는 방식과 동일하게 속성 이름을 사용합니다.  인수가 제공되지 않는 경우 괄호를 생략해도 됩니다.  
  
 `Set` 프로시저를 암시적으로 호출하는 구문은 다음과 같습니다.  
  
 `propertyname[(argumentlist)] = expression`  
  
 `Get` 프로시저를 암시적으로 호출하는 구문은 다음과 같습니다.  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### 선언과 호출에 대한 설명  
 다음 속성은 전체 이름\(fullname\)을 두 부분, 즉 이름\(firstname\)과 성\(lastname\)으로 저장합니다.  호출 코드에서 `fullName`을 만나면 `Get` 프로시저는 두 부분으로 된 이름을 결합하여 전체 이름\(fullname\)을 반환합니다.  호출 코드에서 전체 이름\(fullname\)을 새로 지정하면 `Set` 프로시저가 이 이름을 두 부분으로 나눕니다.  공백이 없으면 전체 이름\(fullname\)이 이름\(firstname\)으로 저장됩니다.  
  
 [!code-vb[VbVbcnProcedures#8](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/property-procedures_1.vb)]  
  
 다음 예제에서는 `fullName`의 property 프로시저를 호출하는 일반적인 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnProcedures#9](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/property-procedures_2.vb)]  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Function 프로시저](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)