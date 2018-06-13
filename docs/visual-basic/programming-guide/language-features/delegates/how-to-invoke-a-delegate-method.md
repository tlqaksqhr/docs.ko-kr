---
title: '방법: 대리자 메서드 호출(Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: aca87dd9fa1990d44c99aab7753f2fd7d508adc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646954"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="3a871-102">방법: 대리자 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a871-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="3a871-103">이 예제에는 하는 메서드는 대리자를 연결 하 고 다음 대리자를 통해 해당 메서드를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a871-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="3a871-104">대리자와 일치 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="3a871-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="3a871-105">라는 대리자를 만들 `MySubDelegate`합니다.</span><span class="sxs-lookup"><span data-stu-id="3a871-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="3a871-106">대리자와 동일한 서명으로 메서드를 포함 하는 클래스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a871-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="3a871-107">대리자의 인스턴스를 만들고 기본 제공을 호출 하 여 해당 대리자와 연결 된 메서드를 호출 하는 메서드를 정의 `Invoke` 메서드.</span><span class="sxs-lookup"><span data-stu-id="3a871-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3a871-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a871-108">See Also</span></span>  
 [<span data-ttu-id="3a871-109">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="3a871-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="3a871-110">대리자</span><span class="sxs-lookup"><span data-stu-id="3a871-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="3a871-111">이벤트</span><span class="sxs-lookup"><span data-stu-id="3a871-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="3a871-112">다중 스레드 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="3a871-112">Multithreaded Applications</span></span>](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
