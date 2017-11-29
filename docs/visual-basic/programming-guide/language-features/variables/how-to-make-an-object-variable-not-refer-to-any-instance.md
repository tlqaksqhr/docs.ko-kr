---
title: "방법: 개체 변수가 인스턴스를 참조하지 않도록 설정(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3b33aef06300bf35b7138ec5b40747532a77140a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a><span data-ttu-id="5d6ea-102">방법: 개체 변수가 인스턴스를 참조하지 않도록 설정(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d6ea-102">How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)</span></span>
<span data-ttu-id="5d6ea-103">로 설정 하 여 개체 인스턴스에서 개체 변수를 분리할 수 [Nothing](../../../../visual-basic/language-reference/nothing.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ea-103">You can disassociate an object variable from any object instance by setting it to [Nothing](../../../../visual-basic/language-reference/nothing.md).</span></span>  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a><span data-ttu-id="5d6ea-104">연결을 끊을 개체 인스턴스에서 개체 변수</span><span class="sxs-lookup"><span data-stu-id="5d6ea-104">To disassociate an object variable from any object instance</span></span>  
  
-   <span data-ttu-id="5d6ea-105">이 변수를 설정 `Nothing` 대입문에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ea-105">Set the variable to `Nothing` in an assignment statement.</span></span>  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a><span data-ttu-id="5d6ea-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5d6ea-106">Robust Programming</span></span>  
 <span data-ttu-id="5d6ea-107">코드에 설정 된 개체 변수의 멤버에 액세스 하려고 할 경우 `Nothing`, <xref:System.NullReferenceException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ea-107">If your code tries to access a member of an object variable that has been set to `Nothing`, a <xref:System.NullReferenceException> occurs.</span></span> <span data-ttu-id="5d6ea-108">개체 변수를 설정 하면 `Nothing` 자주에서 멤버 액세스 하는 것이 좋습니다가 변수는 초기화 되지 않았습니다 가능한 경우 한 `Try...Catch...Finally` 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ea-108">If you set an object variable to `Nothing` frequently, or if it is possible the variable is not initialized, it is a good idea to enclose member accesses in a `Try...Catch...Finally` block.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5d6ea-109">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="5d6ea-109">.NET Framework Security</span></span>  
 <span data-ttu-id="5d6ea-110">기밀 또는 중요 한 데이터를 포함 하는 개체에 대 한 개체 변수를 사용 하는 경우는 변수를 설정할 수 있습니다 `Nothing` 때 처리 하지 않을 적극적으로 이러한 개체 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ea-110">If you use an object variable for objects that contain confidential or sensitive data, you can set the variable to `Nothing` when you are not actively dealing with one of those objects.</span></span> <span data-ttu-id="5d6ea-111">데이터에 액세스 하는 악성 코드의 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6ea-111">This reduces the chance of malicious code gaining access to the data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d6ea-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d6ea-112">See Also</span></span>  
 <xref:System.NullReferenceException>  
 [<span data-ttu-id="5d6ea-113">개체 변수</span><span class="sxs-lookup"><span data-stu-id="5d6ea-113">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="5d6ea-114">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="5d6ea-114">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="5d6ea-115">Nothing</span><span class="sxs-lookup"><span data-stu-id="5d6ea-115">Nothing</span></span>](../../../../visual-basic/language-reference/nothing.md)  
 [<span data-ttu-id="5d6ea-116">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="5d6ea-116">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="5d6ea-117">예외 문제 해결: System.NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="5d6ea-117">Troubleshooting Exceptions: System.NullReferenceException</span></span>](http://msdn.microsoft.com/library/4822b0b4-8105-43fb-887a-3cc51ff02899)
