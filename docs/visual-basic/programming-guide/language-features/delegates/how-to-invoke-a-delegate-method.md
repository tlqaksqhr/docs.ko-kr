---
title: "방법: 대리자 메서드 (Visual Basic)를 호출 합니다. | Microsoft 문서"
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
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 29b20eb6089886c8111711388472004bbacea312
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>방법: 대리자 메서드 호출(Visual Basic)
이 예제에는 메서드는 대리자를 연결 하 고 다음 대리자를 통해 해당 메서드를 호출 하는 방법을 보여 줍니다.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>대리자 및 일치 하는 프로시저 만들기  
  
1.  명명 된 대리자를 만들고 `MySubDelegate`합니다.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  대리자와 동일한 시그니처가 있는 메서드를 포함 하는 클래스를 선언 합니다.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  대리자의 인스턴스를 만들고 기본 제공을 호출 하 여 해당 대리자와 연결 된 메서드를 호출 하는 메서드를 정의 `Invoke` 메서드.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)   
 [다중 스레드 응용 프로그램](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
