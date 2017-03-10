---
title: "Lambda expression will not be removed from this event handler | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc42326"
  - "vbc42326"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42326"
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Lambda expression will not be removed from this event handler
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이벤트 처리기에서 람다 식이 제거되지 않습니다.변수에 람다 식을 할당한 후 변수를 사용하여 이벤트를 추가하거나 제거하십시오.  
  
 이벤트 처리기에 람다 식을 사용할 경우 예기치 않은 동작이 발생할 수 있습니다.  람다 식 정의가 같더라도 컴파일러에서 각 람다 식 정의에 대해 새 메서드를 생성합니다.  따라서 다음 코드를 실행하면 `False`가 표시됩니다.  
  
```vb#  
Module Module1  
  
    Sub Main()  
        Dim fun1 As ChangeInteger = Function(p As Integer) p + 1  
        Dim fun2 As ChangeInteger = Function(p As Integer) p + 1  
        Console.WriteLine(fun1 = fun2)  
    End Sub  
  
    Delegate Function ChangeInteger(ByVal x As Integer) As Integer  
  
End Module  
```  
  
 이벤트 처리기에 람다 식을 사용할 경우 예기치 않은 결과가 발생할 수 있습니다.  다음 예제에서 `AddHandler`로 추가된 람다 식은 `RemoveHandler` 문으로 제거되지 않습니다.  
  
```vb#  
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
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC42326  
  
### 이 오류를 해결하려면  
  
-   경고 메시지를 표시하지 않고 람다 식을 제거하려면 다음 예제와 같이 변수에 람다 식을 할당한 후 `AddHandler` 및 `RemoveHandler` 문에 이 변수를 사용합니다.  
  
    ```vb#  
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
  
## 참고 항목  
 [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)