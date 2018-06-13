---
title: 이벤트 처리기에서 람다 식이 제거되지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- bc42326
- vbc42326
helpviewer_keywords:
- BC42326
ms.assetid: 63214dc6-0112-4245-8ebf-7c9e8f5a5782
ms.openlocfilehash: 69228bbb5f659a8e500e85dea1ef87cb43b0356e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590169"
---
# <a name="lambda-expression-will-not-be-removed-from-this-event-handler"></a><span data-ttu-id="bc3fa-102">이벤트 처리기에서 람다 식이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-102">Lambda expression will not be removed from this event handler</span></span>
<span data-ttu-id="bc3fa-103">이 이벤트 처리기에서 람다 식이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-103">Lambda expression will not be removed from this event handler.</span></span> <span data-ttu-id="bc3fa-104">변수에 람다 식을 할당 하 고 추가 이벤트를 제거 하는 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-104">Assign the lambda expression to a variable and use the variable to add and remove the event.</span></span>  
  
 <span data-ttu-id="bc3fa-105">람다 식을 이벤트 처리기에 사용 되는 경우 예상 하는 동작을 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-105">When lambda expressions are used with event handlers, you may not see the behavior you expect.</span></span> <span data-ttu-id="bc3fa-106">컴파일러는 동일한 경우에 각 람다 식 정의 대 한 새 메서드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-106">The compiler generates a new method for each lambda expression definition, even if they are identical.</span></span> <span data-ttu-id="bc3fa-107">따라서 다음 코드 표시 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-107">Therefore, the following code displays `False`.</span></span>  
  
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
  
 <span data-ttu-id="bc3fa-108">람다 식을 이벤트 처리기를 사용할 때 예기치 않은 결과가 발생할 수 있습니다이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-108">When lambda expressions are used with event handlers, this may cause unexpected results.</span></span> <span data-ttu-id="bc3fa-109">다음 예제에서는 람다 식을 추가 하 여 `AddHandler` 제거 되지 않습니다는 `RemoveHandler` 문.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-109">In the following example, the lambda expression added by `AddHandler` is not removed by the `RemoveHandler` statement.</span></span>  
  
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
  
 <span data-ttu-id="bc3fa-110">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-110">By default, this message is a warning.</span></span> <span data-ttu-id="bc3fa-111">경고를 숨기 거 나 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-111">For more information about how to hide warnings or treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="bc3fa-112">**오류 ID:** BC42326</span><span class="sxs-lookup"><span data-stu-id="bc3fa-112">**Error ID:** BC42326</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bc3fa-113">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bc3fa-113">To correct this error</span></span>  
  
-   <span data-ttu-id="bc3fa-114">경고를 방지를 제거 하 고 람다 식에 변수에 람다 식을 할당 하 고 모두에서 변수 사용의 `AddHandler` 및 `RemoveHandler` 문, 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc3fa-114">To avoid the warning and remove the lambda expression, assign the lambda expression to a variable and use the variable in both the `AddHandler` and `RemoveHandler` statements, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc3fa-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc3fa-115">See Also</span></span>  
 [<span data-ttu-id="bc3fa-116">람다 식</span><span class="sxs-lookup"><span data-stu-id="bc3fa-116">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="bc3fa-117">완화된 대리자 변환</span><span class="sxs-lookup"><span data-stu-id="bc3fa-117">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)  
 [<span data-ttu-id="bc3fa-118">이벤트</span><span class="sxs-lookup"><span data-stu-id="bc3fa-118">Events</span></span>](../../../visual-basic/programming-guide/language-features/events/index.md)
