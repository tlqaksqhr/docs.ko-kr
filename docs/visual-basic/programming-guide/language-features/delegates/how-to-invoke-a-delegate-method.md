---
title: "방법: 대리자 메서드 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea94d4bb26e168667fd75c6928e52261f230c85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="01aba-102">방법: 대리자 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01aba-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="01aba-103">이 예제에는 하는 메서드는 대리자를 연결 하 고 다음 대리자를 통해 해당 메서드를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="01aba-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="01aba-104">대리자와 일치 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="01aba-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="01aba-105">라는 대리자를 만들 `MySubDelegate`합니다.</span><span class="sxs-lookup"><span data-stu-id="01aba-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="01aba-106">대리자와 동일한 서명으로 메서드를 포함 하는 클래스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="01aba-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="01aba-107">대리자의 인스턴스를 만들고 기본 제공을 호출 하 여 해당 대리자와 연결 된 메서드를 호출 하는 메서드를 정의 `Invoke` 메서드.</span><span class="sxs-lookup"><span data-stu-id="01aba-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="01aba-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01aba-108">See Also</span></span>  
 [<span data-ttu-id="01aba-109">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="01aba-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="01aba-110">대리자</span><span class="sxs-lookup"><span data-stu-id="01aba-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="01aba-111">이벤트</span><span class="sxs-lookup"><span data-stu-id="01aba-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="01aba-112">다중 스레드 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="01aba-112">Multithreaded Applications</span></span>](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
