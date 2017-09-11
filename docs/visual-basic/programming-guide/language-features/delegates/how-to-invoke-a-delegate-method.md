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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 060a60da16a0032850b0a45822c8fd24b4622b83
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="c0bd8-102">방법: 대리자 메서드 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="c0bd8-103">이 예제에는 메서드는 대리자를 연결 하 고 다음 대리자를 통해 해당 메서드를 호출 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="c0bd8-104">대리자 및 일치 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="c0bd8-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="c0bd8-105">명명 된 대리자를 만들고 `MySubDelegate`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="c0bd8-106">대리자와 동일한 시그니처가 있는 메서드를 포함 하는 클래스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="c0bd8-107">대리자의 인스턴스를 만들고 기본 제공을 호출 하 여 해당 대리자와 연결 된 메서드를 호출 하는 메서드를 정의 `Invoke` 메서드.</span><span class="sxs-lookup"><span data-stu-id="c0bd8-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c0bd8-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0bd8-108">See Also</span></span>  
 <span data-ttu-id="c0bd8-109">[Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="c0bd8-109">[Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="c0bd8-110"> [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0bd8-110"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="c0bd8-111"> [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="c0bd8-111"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="c0bd8-112"> [다중 스레드 응용 프로그램](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)</span><span class="sxs-lookup"><span data-stu-id="c0bd8-112"> [Multithreaded Applications](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)</span></span>
