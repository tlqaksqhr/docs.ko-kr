---
title: "Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 28c3f84d21f9fbc7e57ba079461194acf7612add
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a>Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여
이러한 예제 공변성 및 반 공변성을 사용 하는 방법을 보여 줍니다는 `Func` 및 `Action` 제네릭 대리자에 메서드를 다시 사용할 수 있게 하 고 코드에 더 많은 유연성을 제공 합니다.  
  
 공 분산과 반공 분산에 대 한 자세한 내용은 참조 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)합니다.  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>공변 형식 매개 변수가 있는 대리자를 사용 하 여  
 다음 예제에서는 제네릭 공변성 (covariance) 지원의 이점을 보여 줍니다. `Func` 대리자입니다. `FindByTitle` 매개 변수를 사용 하는 메서드는 `String` 입력 개체를 반환 하 고는 `Employee` 형식. 그러나이 메서드를 할당할 수 있습니다는 `Func(Of String, Person)` 대리자 `Employee` 상속 `Person`합니다.  
  
```vb  
' Simple hierarchy of classes.  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class Finder  
    Public Shared Function FindByTitle(  
        ByVal title As String) As Employee  
        ' This is a stub for a method that returns  
        ' an employee that has the specified title.  
        Return New Employee  
    End Function  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim findEmployee As Func(Of String, Employee) =  
            AddressOf FindByTitle  
  
        ' The delegate expects a method to return Person,  
        ' but you can assign it a method that returns Employee.  
        Dim findPerson As Func(Of String, Person) =  
            AddressOf FindByTitle  
  
        ' You can also assign a delegate   
        ' that returns a more derived type to a delegate   
        ' that returns a less derived type.  
        findPerson = findEmployee  
    End Sub  
End Class  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>반공 변 형식 매개 변수가 있는 대리자를 사용 하 여  
 다음 예제에서는 제네릭 공변성 지원의 이점을 보여 줍니다. `Action` 대리자입니다. `AddToContacts` 매개 변수를 사용 하는 메서드는 `Person` 유형입니다. 그러나이 메서드를 할당할 수 있습니다는 `Action(Of Employee)` 대리자 `Employee` 상속 `Person`합니다.  
  
```vb  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class AddressBook  
    Shared Sub AddToContacts(ByVal person As Person)  
        ' This method adds a Person object  
        ' to a contact list.  
    End Sub  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim addPersonToContacts As Action(Of Person) =  
            AddressOf AddToContacts  
  
        ' The Action delegate expects   
        ' a method that has an Employee parameter,  
        ' but you can assign it a method that has a Person parameter  
        ' because Employee derives from Person.  
        Dim addEmployeeToContacts As Action(Of Employee) =  
            AddressOf AddToContacts  
  
        ' You can also assign a delegate   
        ' that accepts a less derived parameter   
        ' to a delegate that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>참고 항목  
 [공 분산과 반공 분산 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/covariance-and-contravariance.md)   
 [제네릭](https://msdn.microsoft.com/library/ms172192)
