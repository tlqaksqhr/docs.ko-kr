---
title: 이벤트 처리기에서 람다 식이 제거되지 않습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a4c57d1f8f41d2d9ebb645d3f2628c32a2c4e4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>이벤트 처리기에서 람다 식이 제거되지 않습니다.
이 이벤트 처리기에서 람다 식이 제거 되지 않습니다. 변수에 람다 식을 할당 하 고 추가 이벤트를 제거 하는 변수를 사용 합니다.  
  
 람다 식을 이벤트 처리기에 사용 되는 경우 예상 하는 동작을 나타나지 않을 수 있습니다. 컴파일러는 동일한 경우에 각 람다 식 정의 대 한 새 메서드를 생성 합니다. 따라서 다음 코드 표시 `False`합니다.  
  
```vb  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 람다 식을 이벤트 처리기를 사용할 때 예기치 않은 결과가 발생할 수 있습니다이 있습니다. 다음 예제에서는 람다 식을 추가 하 여 `AddHandler` 제거 되지 않습니다는 `RemoveHandler` 문.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Sub Main()  
  
        ' The following line adds one listener to the event.  
        AddHandler ProcessInteger, Function(m As Integer) m  
  
        ' The following statement searches the current listeners   
        ' for a match to remove. However, this lambda is not the same  
        ' as the previous one, so nothing is removed.  
        RemoveHandler ProcessInteger, Function(m As Integer) m  
  
    End Sub  
End Module  
```  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42326  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   경고를 방지를 제거 하 고 람다 식에 변수에 람다 식을 할당 하 고 모두에서 변수 사용의 `AddHandler` 및 `RemoveHandler` 문, 다음 예제와 같이 합니다.  
  
```vb  
Module Module1  
  
    Event ProcessInteger(ByVal x As Integer)  
  
    Dim PrintHandler As ProcessIntegerEventHandler  
  
    Sub Main()  
  
        ' Assign the lambda expression to a variable.  
        PrintHandler = Function(m As Integer) m  
  
        ' Use the variable to add the listener.  
        AddHandler ProcessInteger, PrintHandler  
  
        ' Use the variable again when you want to remove the listener.  
        RemoveHandler ProcessInteger, PrintHandler  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>참고 항목  
 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [완화된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
