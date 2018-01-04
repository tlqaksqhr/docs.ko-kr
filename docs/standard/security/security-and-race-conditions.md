---
title: "보안 및 경합 상태"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], race conditions
- race conditions
- secure coding, race conditions
- code security, race conditions
ms.assetid: ea3edb80-b2e8-4e85-bfed-311b20cb59b6
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 73664df9c072189f11d451da46bc3019c8593ec9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="security-and-race-conditions"></a><span data-ttu-id="5a0ad-102">보안 및 경합 상태</span><span class="sxs-lookup"><span data-stu-id="5a0ad-102">Security and Race Conditions</span></span>
<span data-ttu-id="5a0ad-103">중요 한 보안 허점 경합 상태에 의해 악용 가능성이 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-103">Another area of concern is the potential for security holes exploited by race conditions.</span></span> <span data-ttu-id="5a0ad-104">여러 가지 방법으로이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-104">There are several ways in which this might happen.</span></span> <span data-ttu-id="5a0ad-105">다음에 나오는 하위 개발자 피해 야 하는 주요 문제 중 일부를 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-105">The subtopics that follow outline some of the major pitfalls that the developer must avoid.</span></span>  
  
## <a name="race-conditions-in-the-dispose-method"></a><span data-ttu-id="5a0ad-106">Dispose 메서드에서 경합 상태</span><span class="sxs-lookup"><span data-stu-id="5a0ad-106">Race Conditions in the Dispose Method</span></span>  
 <span data-ttu-id="5a0ad-107">클래스의 경우 **Dispose** 메서드 (자세한 내용은 참조 [가비지 수집](../../../docs/standard/garbage-collection/index.md))은 동기화 되지 않을 수도 있기 내부 정리 코드 **Dispose** 실행 될 수 있습니다 이상 한 번, 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-107">If a class's **Dispose** method (for more information, see [Garbage Collection](../../../docs/standard/garbage-collection/index.md)) is not synchronized, it is possible that cleanup code inside **Dispose** can be run more than once, as shown in the following example.</span></span>  
  
```vb  
Sub Dispose()  
    If Not (myObj Is Nothing) Then  
       Cleanup(myObj)  
       myObj = Nothing  
    End If  
End Sub  
```  
  
```csharp  
void Dispose()   
{  
    if( myObj != null )   
    {  
        Cleanup(myObj);  
        myObj = null;  
    }  
}  
```  
  
 <span data-ttu-id="5a0ad-108">때문에이 **Dispose** 구현은 동기화 되지 않으면는 `Cleanup` 첫 번째 스레드 및 하기 전에 두 번째 스레드가 호출 될 `_myObj` 로 설정 된 **null**합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-108">Because this **Dispose** implementation is not synchronized, it is possible for `Cleanup` to be called by first one thread and then a second thread before `_myObj` is set to **null**.</span></span> <span data-ttu-id="5a0ad-109">수행 되는 작업에 따라 달라 집니다이 보안 문제 인지 때는 `Cleanup` 코드를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-109">Whether this is a security concern depends on what happens when the `Cleanup` code runs.</span></span> <span data-ttu-id="5a0ad-110">와 동기화 되지 않은 중요 한 문제 **Dispose** 구현 파일 같은 리소스 핸들의 사용이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-110">A major issue with unsynchronized **Dispose** implementations involves the use of resource handles such as files.</span></span> <span data-ttu-id="5a0ad-111">메서드를 잘못 하면 잘못 된 핸들이 사용할 수 있으며이 보안 취약점으로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-111">Improper disposal can cause the wrong handle to be used, which often leads to security vulnerabilities.</span></span>  
  
## <a name="race-conditions-in-constructors"></a><span data-ttu-id="5a0ad-112">생성자의 경합 상태</span><span class="sxs-lookup"><span data-stu-id="5a0ad-112">Race Conditions in Constructors</span></span>  
 <span data-ttu-id="5a0ad-113">일부 응용 프로그램에서 다른 스레드를 클래스 생성자가 완전히 실행 하기 전에 클래스 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-113">In some applications, it might be possible for other threads to access class members before their class constructors have completely run.</span></span> <span data-ttu-id="5a0ad-114">이 발생 하거나 필요한 경우 스레드를 동기화 해야 하는 경우 보안 문제가 없는지를 확인 하기 위해 모든 클래스 생성자를 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-114">You should review all class constructors to make sure that there are no security issues if this should happen, or synchronize threads if necessary.</span></span>  
  
## <a name="race-conditions-with-cached-objects"></a><span data-ttu-id="5a0ad-115">캐시 된 개체와 경합 상태</span><span class="sxs-lookup"><span data-stu-id="5a0ad-115">Race Conditions with Cached Objects</span></span>  
 <span data-ttu-id="5a0ad-116">보안 정보를 캐시 하거나 코드 액세스 보안을 사용 하는 코드 [Assert](../../../docs/framework/misc/using-the-assert-method.md) 작업이 노출 될 수 있습니다 경합 상태에는 클래스의 다른 부분 적절 하 게 동기화 되지 않은 경우 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-116">Code that caches security information or uses the code access security [Assert](../../../docs/framework/misc/using-the-assert-method.md) operation might also be vulnerable to race conditions if other parts of the class are not appropriately synchronized, as shown in the following example.</span></span>  
  
```vb  
Sub SomeSecureFunction()  
    If SomeDemandPasses() Then  
        fCallersOk = True  
        DoOtherWork()  
        fCallersOk = False()  
    End If  
End Sub  
  
Sub DoOtherWork()  
    If fCallersOK Then  
        DoSomethingTrusted()  
    Else  
        DemandSomething()  
        DoSomethingTrusted()  
    End If  
End Sub  
```  
  
```csharp  
void SomeSecureFunction()   
{  
    if(SomeDemandPasses())   
    {  
        fCallersOk = true;  
        DoOtherWork();  
        fCallersOk = false();  
    }  
}  
void DoOtherWork()   
{  
    if( fCallersOK )   
    {  
        DoSomethingTrusted();  
    }  
    else   
    {  
        DemandSomething();  
        DoSomethingTrusted();  
    }  
}  
```  
  
 <span data-ttu-id="5a0ad-117">다른 경로가 있으면 `DoOtherWork` 같은 개체와 다른 스레드에서 호출할 수 있는, 요청을 지 나 신뢰할 수 없는 호출자 지연 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-117">If there are other paths to `DoOtherWork` that can be called from another thread with the same object, an untrusted caller can slip past a demand.</span></span>  
  
 <span data-ttu-id="5a0ad-118">코드 보안 정보를 캐시 하는 경우이 취약점에 대 한 검토 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-118">If your code caches security information, make sure that you review it for this vulnerability.</span></span>  
  
## <a name="race-conditions-in-finalizers"></a><span data-ttu-id="5a0ad-119">종료자의 경합 상태</span><span class="sxs-lookup"><span data-stu-id="5a0ad-119">Race Conditions in Finalizers</span></span>  
 <span data-ttu-id="5a0ad-120">경합 상태 종료자에서 해제 하는 정적 또는 관리 되지 않는 리소스를 참조 하는 개체에도 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-120">Race conditions can also occur in an object that references a static or unmanaged resource that it then frees in its finalizer.</span></span> <span data-ttu-id="5a0ad-121">여러 개체 클래스의 종료자에서 조작 되는 리소스를 공유 하는 경우 개체에 해당 리소스에 대 한 모든 액세스를 동기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a0ad-121">If multiple objects share a resource that is manipulated in a class's finalizer, the objects must synchronize all access to that resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0ad-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a0ad-122">See Also</span></span>  
 [<span data-ttu-id="5a0ad-123">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="5a0ad-123">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
