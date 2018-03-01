---
title: "예외 처리 보안"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
helpviewer_keywords:
- code security, exception handling
- security [.NET Framework], exception handling
- secure coding, exception handling
- exception handling, security
ms.assetid: 1f3da743-9742-47ff-96e6-d0dd1e9e1c19
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 548606a0196012fdd21bf5512e8ea7b089c723ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="securing-exception-handling"></a><span data-ttu-id="6c277-102">예외 처리 보안</span><span class="sxs-lookup"><span data-stu-id="6c277-102">Securing Exception Handling</span></span>
<span data-ttu-id="6c277-103">Visual c + + 및 Visual Basic에서 스택 추가 필터 식을 전에 실행할 **마지막** 문.</span><span class="sxs-lookup"><span data-stu-id="6c277-103">In Visual C++ and Visual Basic, a filter expression further up the stack runs before any **finally** statement.</span></span> <span data-ttu-id="6c277-104">**catch** 블록에 연결 된 후 실행 되는 해당 필터는 **마지막** 문.</span><span class="sxs-lookup"><span data-stu-id="6c277-104">The **catch** block associated with that filter runs after the **finally** statement.</span></span> <span data-ttu-id="6c277-105">자세한 내용은 참조 [사용자 필터 예외](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-105">For more information, see [Using User-Filtered Exceptions](../../../docs/standard/exceptions/using-user-filtered-exception-handlers.md).</span></span> <span data-ttu-id="6c277-106">이 섹션에서는이 순서에 따른 보안 위험을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-106">This section examines the security implications of this order.</span></span> <span data-ttu-id="6c277-107">다음 의사 코드 예제에서는 필터 문 순서를 보여 줍니다 및 **마지막** 문을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-107">Consider the following pseudocode example that illustrates the order in which filter statements and **finally** statements run.</span></span>  
  
```cpp  
void Main()   
{  
    try   
    {  
        Sub();  
    }   
    except (Filter())   
    {  
        Console.WriteLine("catch");  
    }  
}  
bool Filter () {  
    Console.WriteLine("filter");  
    return true;  
}  
void Sub()   
{  
    try   
    {  
        Console.WriteLine("throw");  
        throw new Exception();  
    }   
    finally   
    {  
        Console.WriteLine("finally");  
    }  
}                        
```  
  
 <span data-ttu-id="6c277-108">이 코드에서는 다음이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-108">This code prints the following.</span></span>  
  
```  
Throw  
Filter  
Finally  
Catch  
```  
  
 <span data-ttu-id="6c277-109">필터가 먼저 실행는 **마지막** 문, 여기서 다른 코드를 실행 하는 데 이용 변경 상태를 수행 하면 보안 문제를 유발 될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-109">The filter runs before the **finally** statement, so security issues can be introduced by anything that makes a state change where execution of other code could take advantage.</span></span> <span data-ttu-id="6c277-110">예:</span><span class="sxs-lookup"><span data-stu-id="6c277-110">For example:</span></span>  
  
```cpp  
try   
{  
    Alter_Security_State();  
    // This means changing anything (state variables,  
    // switching unmanaged context, impersonation, and   
    // so on) that could be exploited if malicious   
    // code ran before state is restored.  
    Do_some_work();  
}   
finally   
{  
    Restore_Security_State();  
    // This simply restores the state change above.  
}  
```  
  
 <span data-ttu-id="6c277-111">이 의사 코드에서는 임의의 코드를 실행 하기 위해 스택의 상위 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-111">This pseudocode allows a filter higher up the stack to run arbitrary code.</span></span> <span data-ttu-id="6c277-112">비슷한 영향을 미칠 수 있는 작업의 다른 예제는 임시 일부 보안 검사를 무시 하는 내부 플래그를 설정 하는 다른 id 가장 하거나 스레드와 연결 된 문화권을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-112">Other examples of operations that would have a similar effect are temporary impersonation of another identity, setting an internal flag that bypasses some security check, or changing the culture associated with the thread.</span></span> <span data-ttu-id="6c277-113">권장된 솔루션 호출자의 필터 블록에서 스레드 상태에는 코드의 변경 내용을 격리 하는 예외 처리기를 도입 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-113">The recommended solution is to introduce an exception handler to isolate the code's changes to thread state from callers' filter blocks.</span></span> <span data-ttu-id="6c277-114">그러나이 예외 처리기 제대로 도입 될 중요 하거나이 문제가 해결 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-114">However, it is important that the exception handler be properly introduced or this problem will not be fixed.</span></span> <span data-ttu-id="6c277-115">다음 예제에서는 UI 문화권을 전환 하지만 모든 종류의 스레드 상태 변경 마찬가지로 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-115">The following example switches the UI culture, but any kind of thread state change could be similarly exposed.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
   CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
   try {  
      Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
      // Do something that throws an exception.  
}  
   finally {  
      Thread.CurrentThread.CurrentUICulture = saveCulture;  
   }  
}  
```  
  
```vb  
Public Class UserCode  
   Public Shared Sub Main()  
      Try  
         Dim obj As YourObject = new YourObject  
         obj.YourMethod()  
      Catch e As Exception When FilterFunc  
         Console.WriteLine("An error occurred: '{0}'", e)  
         Console.WriteLine("Current Culture: {0}",   
Thread.CurrentThread.CurrentUICulture)  
      End Try  
   End Sub  
  
   Public Function FilterFunc As Boolean  
      Console.WriteLine("Current Culture: {0}", Thread.CurrentThread.CurrentUICulture)  
      Return True  
   End Sub  
  
End Class  
```  
  
 <span data-ttu-id="6c277-116">올바른 수정이 경우 기존 래핑하는 **시도**/**마지막** 블록는 **시도**/**catch** 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-116">The correct fix in this case is to wrap the existing **try**/**finally** block in a **try**/**catch** block.</span></span> <span data-ttu-id="6c277-117">소개는 **catch throw** 기존 절 **시도**/**마지막** 블록 다음 예제에 표시 된 대로 문제를 해결 되지 않으면 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-117">Simply introducing a **catch-throw** clause into the existing **try**/**finally** block does not fix the problem, as shown in the following example.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
  
    try   
    {  
        Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
        // Do something that throws an exception.  
    }  
    catch { throw; }  
    finally   
    {  
        Thread.CurrentThread.CurrentUICulture = saveCulture;  
    }  
}  
```  
  
 <span data-ttu-id="6c277-118">때문에 문제가 해결 되지 않으면는 **마지막** 하기 전에 문이 실행 되지 않은 `FilterFunc` 컨트롤을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-118">This does not fix the problem because the **finally** statement has not run before the `FilterFunc` gets control.</span></span>  
  
 <span data-ttu-id="6c277-119">다음 예제는 다음을 통해 문제를 해결는 **마지막** 절이 호출자의 예외 필터 블록에 예외를 제공 하기 전에 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c277-119">The following example fixes the problem by ensuring that the **finally** clause has executed before offering an exception up the callers' exception filter blocks.</span></span>  
  
```cpp  
YourObject.YourMethod()  
{  
    CultureInfo saveCulture = Thread.CurrentThread.CurrentUICulture;  
    try    
    {  
        try   
        {  
            Thread.CurrentThread.CurrentUICulture = new CultureInfo("de-DE");  
            // Do something that throws an exception.  
        }  
        finally   
        {  
            Thread.CurrentThread.CurrentUICulture = saveCulture;  
        }  
    }  
    catch { throw; }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6c277-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c277-120">See Also</span></span>  
 [<span data-ttu-id="6c277-121">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="6c277-121">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
