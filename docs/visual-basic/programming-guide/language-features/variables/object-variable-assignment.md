---
title: "개체 변수 할당(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Nothing keyword [Visual Basic], object variable assignment
- object variables [Visual Basic], initializing
- variables [Visual Basic], initializing
- objects [Visual Basic], current instance
- object variables [Visual Basic], assigning
- variables [Visual Basic], object variables
- current instance [Visual Basic], defined
- variables [Visual Basic], assigning
- assignment statements [Visual Basic], object variable assignment
- Me keyword [Visual Basic], as object variable
ms.assetid: 3706811d-fd40-44fe-8727-d692e8e55d6d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: eb6b53bebddc1c9cf1b9088e96ded36a5e1c5242
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-assignment-visual-basic"></a>개체 변수 할당(Visual Basic)
일반적인 대입문을 사용 하 여 개체 변수에 개체를 할당 합니다. 개체 식을 할당할 수 있습니다 또는 [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드를 다음 예제와 같이 보여 줍니다.  
  
```  
Dim thisObject As Object  
' The following statement assigns an object reference.  
thisObject = Form1  
' The following statement discontinues association with any object.  
thisObject = Nothing  
```  
  
 `Nothing`변수에 할당 된 현재 개체가 없는 것을 의미 합니다.  
  
## <a name="initialization"></a>초기화  
 코드를 실행 하 고 변수가 초기화 됩니다 개체를 시작할 때 `Nothing`합니다. 해당 선언 초기화를 포함 하는 것 다시 선언 문이 실행 될 때 지정 된 값으로 초기화 됩니다.  
  
 사용 하 여 선언에서 초기화를 포함할 수는 [새로](../../../../visual-basic/language-reference/operators/new-operator.md) 키워드입니다. 개체 변수를 선언 하는 다음 선언문 `testUri` 및 `ver` 하 고 특정 개체를 할당 합니다. 각를 사용 하 여 해당 클래스의 오버 로드 된 생성자 중 하나는 개체를 초기화 합니다.  
  
```  
Dim testUri As New System.Uri("http://www.microsoft.com")  
Dim ver As New System.Version(6, 1, 0)  
```  
  
## <a name="disassociation"></a>연결 해제  
 개체 변수 설정 `Nothing` 특정 개체 변수 연결이 해제 합니다. 이렇게 하면 실수로 개체 변수를 변경 하 여 변경 하는 없습니다. 또한 개체 변수는 다음 예제와 같이 유효한 개체를 가리키는 여부를 테스트할 수 있습니다.  
  
```  
If otherObject IsNot Nothing Then  
    ' otherObject refers to a valid object, so your code can use it.  
End If  
```  
  
 변수가 가리키는 개체를 다른 응용 프로그램에 있으면,이 테스트는 해당 응용 프로그램 종료 했거나 개체만 개체를 무효화 하는지 여부를 확인할 수 없습니다.  
  
 개체 변수 값이 `Nothing` 라고도 *null 참조*합니다.  
  
## <a name="current-instance"></a>현재 인스턴스  
 *현재 인스턴스가* 는 코드가 현재 실행 중인 개체입니다. 프로시저 내의 모든 코드가 실행 되는 프로시저가 호출 된 현재 인스턴스의 됩니다.  
  
 `Me` 현재 인스턴스를 참조 하는 개체 변수로 키워드를 적용 합니다. 프로시저 없으면 [공유](../../../../visual-basic/language-reference/modifiers/shared.md), 사용할 수 있습니다는 `Me` 키워드 현재 인스턴스에 대 한 포인터를 가져올 수 있습니다. 공유 프로시저 클래스의 특정 인스턴스에 연결할 수 없습니다.  
  
 사용 하 여 `Me` 프로시저 다른 모듈에서 현재 인스턴스를 전달 하는 데 특히 유용 합니다. 예를 들어 XML 문서 수가 및 일부 표준 텍스트를 모두 추가. 다음 예제에서는이 작업을 수행 하는 절차를 정의 합니다.  
  
```  
Sub addStandardText(XmlDoc As System.Xml.XmlDocument)  
    XmlDoc.CreateTextNode("This text goes into every XML document.")  
End Sub  
```  
  
 그런 다음 모든 XML 문서 개체 프로시저를 호출 하 고 현재 인스턴스를 인수로 전달할 수 없습니다. 다음은 이에 대한 예입니다.  
  
```  
addStandardText(Me)  
```  
  
## <a name="see-also"></a>참고 항목  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [방법: Visual Basic의 개체를 할당 하 고 개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [방법: 개체 변수가 인스턴스를 참조하지 않도록 설정](../../../../visual-basic/programming-guide/language-features/variables/how-to-make-an-object-variable-not-refer-to-any-instance.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
