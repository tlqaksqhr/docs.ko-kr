---
title: "(Visual Basic) 대리자의 가변성 사용 | Microsoft 문서"
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
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
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
ms.openlocfilehash: 620fd61000e42d68f566e441d023d73a036000ae
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="using-variance-in-delegates-visual-basic"></a><span data-ttu-id="c30d1-102">(Visual Basic) 대리자의 가변성 사용</span><span class="sxs-lookup"><span data-stu-id="c30d1-102">Using Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="c30d1-103">메서드를 대리자에 할당할 때 *공변성 (covariance)* 및 *반 공변성* 대리자 형식을 메서드 시그니처와 일치 하는 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-103">When you assign a method to a delegate, *covariance* and *contravariance* provide flexibility for matching a delegate type with a method signature.</span></span> <span data-ttu-id="c30d1-104">공변성 (covariance)은 대리자에 정의 된 것 보다 더 많이 파생 된 반환 형식을 갖는 메서드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-104">Covariance permits a method to have return type that is more derived than that defined in the delegate.</span></span> <span data-ttu-id="c30d1-105">반공 분산 된 대리자 형식에 있는 것 보다 더 적게 파생 된 매개 변수 형식을 가진 메서드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-105">Contravariance permits a method that has parameter types that are less derived than those in the delegate type.</span></span>  
  
## <a name="example-1-covariance"></a><span data-ttu-id="c30d1-106">예 1: 공변성 (covariance)</span><span class="sxs-lookup"><span data-stu-id="c30d1-106">Example 1: Covariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="c30d1-107">설명</span><span class="sxs-lookup"><span data-stu-id="c30d1-107">Description</span></span>  
 <span data-ttu-id="c30d1-108">이 예제는 대리자 시그니처에 반환 형식에서 파생 된 반환 형식을 포함 하는 메서드로 대리자를 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-108">This example demonstrates how delegates can be used with methods that have return types that are derived from the return type in the delegate signature.</span></span> <span data-ttu-id="c30d1-109">반환 된 데이터 형식 `DogsHandler` 형식의 `Dogs`에서 파생 되는 `Mammals` 대리자에서 정의 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-109">The data type returned by `DogsHandler` is of type `Dogs`, which derives from the `Mammals` type that is defined in the delegate.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c30d1-110">코드</span><span class="sxs-lookup"><span data-stu-id="c30d1-110">Code</span></span>  
  
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
  
## <a name="example-2-contravariance"></a><span data-ttu-id="c30d1-111">예제 2: 반공 분산</span><span class="sxs-lookup"><span data-stu-id="c30d1-111">Example 2: Contravariance</span></span>  
  
### <a name="description"></a><span data-ttu-id="c30d1-112">설명</span><span class="sxs-lookup"><span data-stu-id="c30d1-112">Description</span></span>  
 <span data-ttu-id="c30d1-113">이 예제에서는 대리자 서명 매개 변수 형식의 기본 형식이 되는 형식 매개 변수를 포함 하는 메서드가 대리자를 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-113">This example demonstrates how delegates can be used with methods that have parameters of a type that are base types of the delegate signature parameter type.</span></span> <span data-ttu-id="c30d1-114">반 공변성을 통해 별도 처리기는 대신 하나의 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-114">With contravariance, you can use one event handler instead of separate handlers.</span></span> <span data-ttu-id="c30d1-115">예를 들어 허용 하는 이벤트 처리기를 만들 수 있습니다는 `EventArgs` 함께 사용해 서 입력 매개 변수는 `Button.MouseClick` 이벤트를 전송 하는 `MouseEventArgs` 형식 매개 변수로도 `TextBox.KeyDown` 이벤트를 보내는 `KeyEventArgs` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="c30d1-115">For example, you can create an event handler that accepts an `EventArgs` input parameter and use it with a `Button.MouseClick` event that sends a `MouseEventArgs` type as a parameter, and also with a `TextBox.KeyDown` event that sends a `KeyEventArgs` parameter.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c30d1-116">코드</span><span class="sxs-lookup"><span data-stu-id="c30d1-116">Code</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c30d1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c30d1-117">See Also</span></span>  
 <span data-ttu-id="c30d1-118">[(Visual Basic) 대리자의 가변성](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span><span class="sxs-lookup"><span data-stu-id="c30d1-118">[Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) </span></span>  
<span data-ttu-id="c30d1-119"> [Func 및 Action 제네릭 대리자 (Visual Basic)에 대 한 분산을 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="c30d1-119"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
