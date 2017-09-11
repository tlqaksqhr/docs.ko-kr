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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b4dc4a162d3562b218a448653cb51473fff4165a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a><span data-ttu-id="10e31-102">Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="10e31-102">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>
<span data-ttu-id="10e31-103">이러한 예제 공변성 및 반 공변성을 사용 하는 방법을 보여 줍니다는 `Func` 및 `Action` 제네릭 대리자에 메서드를 다시 사용할 수 있게 하 고 코드에 더 많은 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="10e31-103">These examples demonstrate how to use covariance and contravariance in the `Func` and `Action` generic delegates to enable reuse of methods and provide more flexibility in your code.</span></span>  
  
 <span data-ttu-id="10e31-104">공 분산과 반공 분산에 대 한 자세한 내용은 참조 [대리자 (Visual Basic)에 대 한 분산](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="10e31-104">For more information about covariance and contravariance, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).</span></span>  
  
## <a name="using-delegates-with-covariant-type-parameters"></a><span data-ttu-id="10e31-105">공변 형식 매개 변수가 있는 대리자를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="10e31-105">Using Delegates with Covariant Type Parameters</span></span>  
 <span data-ttu-id="10e31-106">다음 예제에서는 제네릭 공변성 (covariance) 지원의 이점을 보여 줍니다. `Func` 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="10e31-106">The following example illustrates the benefits of covariance support in the generic `Func` delegates.</span></span> <span data-ttu-id="10e31-107">`FindByTitle` 매개 변수를 사용 하는 메서드는 `String` 입력 개체를 반환 하 고는 `Employee` 형식.</span><span class="sxs-lookup"><span data-stu-id="10e31-107">The `FindByTitle` method takes a parameter of the `String` type and returns an object of the `Employee` type.</span></span> <span data-ttu-id="10e31-108">그러나이 메서드를 할당할 수 있습니다는 `Func(Of String, Person)` 대리자 `Employee` 상속 `Person`합니다.</span><span class="sxs-lookup"><span data-stu-id="10e31-108">However, you can assign this method to the `Func(Of String, Person)` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="using-delegates-with-contravariant-type-parameters"></a><span data-ttu-id="10e31-109">반공 변 형식 매개 변수가 있는 대리자를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="10e31-109">Using Delegates with Contravariant Type Parameters</span></span>  
 <span data-ttu-id="10e31-110">다음 예제에서는 제네릭 공변성 지원의 이점을 보여 줍니다. `Action` 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="10e31-110">The following example illustrates the benefits of contravariance support in the generic `Action` delegates.</span></span> <span data-ttu-id="10e31-111">`AddToContacts` 매개 변수를 사용 하는 메서드는 `Person` 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="10e31-111">The `AddToContacts` method takes a parameter of the `Person` type.</span></span> <span data-ttu-id="10e31-112">그러나이 메서드를 할당할 수 있습니다는 `Action(Of Employee)` 대리자 `Employee` 상속 `Person`합니다.</span><span class="sxs-lookup"><span data-stu-id="10e31-112">However, you can assign this method to the `Action(Of Employee)` delegate because `Employee` inherits `Person`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="10e31-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10e31-113">See Also</span></span>  
 <span data-ttu-id="10e31-114">[공 분산과 반공 분산 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/covariance-and-contravariance.md) </span><span class="sxs-lookup"><span data-stu-id="10e31-114">[Covariance and Contravariance (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/covariance-and-contravariance.md) </span></span>  
<span data-ttu-id="10e31-115"> [제네릭](https://msdn.microsoft.com/library/ms172192)</span><span class="sxs-lookup"><span data-stu-id="10e31-115"> [Generics](https://msdn.microsoft.com/library/ms172192)</span></span>
