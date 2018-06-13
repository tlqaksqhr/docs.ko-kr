---
title: (Visual Basic) 대리자의 가변성 사용
ms.date: 07/20/2015
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
ms.openlocfilehash: c2390d95bd6bab9f5625c6ec08c374f469f1fc55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644136"
---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="f1d05-102">(Visual Basic) 대리자의 가변성 사용</span><span class="sxs-lookup"><span data-stu-id="f1d05-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="f1d05-103">메서드를 대리자에 할당하면 *공변성(covariance)* 및 *반공변성(Contravariance)* 은 대리자 형식과 메서드 시그니처의 일치를 확인하는 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="f1d05-104">공변성(covariance)은 메서드가 대리자에 정의된 것보다 더 많은 수의 파생된 형식을 반환하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="f1d05-105">반공변성(contravariance)은 메서드가 대리자 형식보다 더 적은 수의 파생된 매개 변수 형식을 갖도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="f1d05-106">예제 1: 공변성(Covariance)</span><span class="sxs-lookup"><span data-stu-id="f1d05-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="f1d05-107">설명</span><span class="sxs-lookup"><span data-stu-id="f1d05-107">Description</span></span>  
 <span data-ttu-id="f1d05-108">이 예제에서는 대리자를 대리자 시그니처의 반환 형식에서 파생된 반환 형식이 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="f1d05-109">`DogsHandler`에서 반환된 데이터 형식은 `Dogs`이고, 이 형식은 대리자에 정의된 `Mammals` 형식에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f1d05-110">코드</span><span class="sxs-lookup"><span data-stu-id="f1d05-110">Code</span></span>  
  
```vb  
Class Mammals  
End Class  
  
Class Dogs  
    Inherits Mammals  
End Class  
Class Test  
    Public Delegate Function HandlerMethod() As Mammals  
    Public Shared Function MammalsHandler() As Mammals  
        Return Nothing  
    End Function  
    Public Shared Function DogsHandler() As Dogs  
        Return Nothing  
    End Function  
    Sub Test()  
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler  
        ' Covariance enables this assignment.  
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler  
    End Sub  
End Class  
```  
  
## <a name="example-2-contravariance"></a><span data-ttu-id="f1d05-111">예제 2: 반공변성(Contravariance)</span><span class="sxs-lookup"><span data-stu-id="f1d05-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="f1d05-112">설명</span><span class="sxs-lookup"><span data-stu-id="f1d05-112">Description</span></span>  
 <span data-ttu-id="f1d05-113">이 예제에서는 대리자를 대리자 시그니처 매개 변수 형식의 기본 형식인 형식 매개 변수를 가지고 있는 메서드와 함께 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="f1d05-114">반공변성(contravariance)에서는 별도의 여러 처리기 대신 하나의 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="f1d05-115">예를 들어 `EventArgs` 입력 매개 변수를 수락하고, 매개 변수로서 `MouseEventArgs` 형식을 전송하는 `Button.MouseClick` 이벤트 및 `KeyEventArgs` 매개 변수를 전송하는 `TextBox.KeyDown` 이벤트와 함께 사용하는 이벤트 처리기를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1d05-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f1d05-116">코드</span><span class="sxs-lookup"><span data-stu-id="f1d05-116">Code</span></span>  
  
```vb  
' Event hander that accepts a parameter of the EventArgs type.  
Private Sub MultiHandler(ByVal sender As Object,  
                         ByVal e As System.EventArgs)  
    Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Form1_Load(ByVal sender As System.Object,  
    ByVal e As System.EventArgs) Handles MyBase.Load  
  
    ' You can use a method that has an EventArgs parameter,  
    ' although the event expects the KeyEventArgs parameter.  
    AddHandler Button1.KeyDown, AddressOf MultiHandler  
  
    ' You can use the same method   
    ' for the event that expects the MouseEventArgs parameter.  
    AddHandler Button1.MouseClick, AddressOf MultiHandler  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1d05-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1d05-117">See Also</span></span>  
 [<span data-ttu-id="f1d05-118">대리자의 가변성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1d05-118">Variance in Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)  
 [<span data-ttu-id="f1d05-119">Func 및 Action 제네릭 대리자에 가변성 사용(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f1d05-119">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
