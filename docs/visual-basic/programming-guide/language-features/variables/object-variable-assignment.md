---
title: "Object Variable Assignment (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Nothing keyword, object variable assignment"
  - "object variables, initializing"
  - "variables [Visual Basic], initializing"
  - "objects [Visual Basic], current instance"
  - "object variables, assigning"
  - "variables [Visual Basic], object variables"
  - "current instance, defined"
  - "variables [Visual Basic], assigning"
  - "assignment statements, object variable assignment"
  - "Me keyword, as object variable"
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Object Variable Assignment (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체를 개체 변수에 할당하려면 일반적인 대입문을 사용합니다.  다음 예제와 같이 개체 식이나 [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드를 할당할 수 있습니다.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing`은 현재 변수에 할당된 개체가 없음을 의미합니다.  
  
## 초기화  
 코드가 실행되면 개체 변수가 `Nothing`으로 초기화됩니다.  선언에 초기화가 포함된 개체 변수는 선언문이 실행될 때 지정한 값으로 다시 초기화됩니다.  
  
 [New](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드를 사용하여 선언에 초기화를 포함할 수 있습니다.  다음 선언문은 개체 변수 `testUri` 및 `ver`를 선언하고 여기에 특정 개체를 할당합니다.  각각 적절한 클래스의 오버로드된 생성자 중 하나를 사용하여 개체를 초기화합니다.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## 연결 해제  
 개체 변수를 `Nothing`으로 설정하면 해당 변수와 특정 개체 사이의 연결이 해제됩니다.  이렇게 하면 실수로 변수를 변경하여 개체가 변경되는 것을 방지할 수 있습니다.  또한 다음 예제와 같이 개체 변수가 유효한 개체를 가리키는지 여부를 테스트할 수도 있습니다.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 변수가 참조하는 개체가 다른 응용 프로그램에 있는 경우에는 이 테스트를 통해 해당 응용 프로그램이 종료되었는지 또는 개체만 무효화되었는지 여부를 확인할 수 없습니다.  
  
 `Nothing` 값이 있는 개체 변수를 *null 참조*라고도 합니다.  
  
## 현재 인스턴스  
 개체의 *현재 인스턴스*는 코드가 현재 실행 중인 인스턴스입니다.  모든 코드는 프로시저 내에서 실행되므로 현재 인스턴스는 프로시저가 호출된 인스턴스입니다.  
  
 `Me` 키워드는 현재 인스턴스를 참조하는 개체 변수로 적용됩니다.  [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)가 아닌 프로시저의 경우 `Me` 키워드를 사용하여 현재 인스턴스에 대한 포인터를 얻을 수 있습니다.  공유 프로시저는 클래스의 특정 인스턴스와 연결할 수 없습니다.  
  
 현재 인스턴스를 다른 모듈의 프로시저로 전달하려는 경우 `Me`를 사용하면 유용합니다.  예를 들어, 여러 XML 문서 모두에 몇 개의 표준 텍스트를 추가하려는 경우  다음 예제와 같은 프로시저를 정의할 수 있습니다.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 모든 XML 문서 개체는 프로시저를 호출하고 현재 인스턴스를 인수로 전달할 수 있습니다.  다음 예제에서는 이 작업을 보여 줍니다.  
  
```  
addStandardText(Me)  
```  
  
## 참고 항목  
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [How to: Declare an Object Variable and Assign an Object to It in Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)   
 [How to: Make an Object Variable Not Refer to Any Instance](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)