---
title: "이 이벤트 처리기에서 람다 식이 제거 되지 것입니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42326
- vbc42326
dev_langs:
- VB
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bdf7ad8f8a116c818e72d67150d72d0c96a4dc3b
ms.lasthandoff: 03/13/2017

---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a>이벤트 처리기에서 람다 식이 제거되지 않습니다.
이벤트 처리기에서 람다 식이 제거되지 않습니다. 람다 식을 변수에 할당 하 고 변수를 사용 하 여 추가 하 고 이벤트를 제거 합니다.  
  
 람다 식을 이벤트 처리기를 사용할 때 예상 하는 동작을 보이지 않을 수도 있습니다. 컴파일러는 동일한 경우에 각 람다 식 정의 대 한 새 메서드를 생성 합니다. 따라서 다음 코드를 표시 `False`합니다.  
  
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
  
 람다 식을 이벤트 처리기를 사용할 때 예기치 않은 결과가 발생할 수 있습니다이 있습니다. 다음 예제에서는 람다 식을 추가 하 여 `AddHandler` 에 의해 제거 하지는 `RemoveHandler` 문.  
  
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
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** BC42326  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   경고를 방지 하 고 람다 식을 제거 하려면 람다 식을 변수에 할당 하 고 변수를 사용 하 여 모두에 `AddHandler` 및 `RemoveHandler` 문, 다음 예제와 같이 합니다.  
  
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
 [완화 된 대리자 변환](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)   
 [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
