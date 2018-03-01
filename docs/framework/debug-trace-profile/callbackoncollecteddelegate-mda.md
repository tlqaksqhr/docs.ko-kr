---
title: callbackOnCollectedDelegate MDA
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
- MDAs (managed debugging assistants), garbage collection
- managed debugging assistants (MDAs), callback on collected delegates
- MDAs (managed debugging assistants), callback on collected delegates
- callback on delegate after garbage collection
- callbackOnCollectedDelegate MDA
- managed debugging assistants (MDAs), garbage collection
- call back collected delegates
- garbage collection, run-time errors
- delegates [.NET Framework], garbage collection
ms.assetid: 398b0ce0-5cc9-4518-978d-b8263aa21e5b
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5459efbb07aa235bd7c1d34ffd6b56195fe0bf1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="callbackoncollecteddelegate-mda"></a><span data-ttu-id="b92ea-102">callbackOnCollectedDelegate MDA</span><span class="sxs-lookup"><span data-stu-id="b92ea-102">callbackOnCollectedDelegate MDA</span></span>
<span data-ttu-id="b92ea-103">대리자가 함수 포인터로 관리 코드에서 비관리 코드로 마샬링되고 대리자가 가비지 수집된 후 콜백이 해당 함수 포인터에 배치된 경우 `callbackOnCollectedDelegate` MDA(관리 디버깅 도우미)가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-103">The `callbackOnCollectedDelegate` managed debugging assistant (MDA) is activated if a delegate is marshaled from managed to unmanaged code as a function pointer and a callback is placed on that function pointer after the delegate has been garbage collected.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b92ea-104">증상</span><span class="sxs-lookup"><span data-stu-id="b92ea-104">Symptoms</span></span>  
 <span data-ttu-id="b92ea-105">관리되는 대리자에서 가져온 함수 포인터를 통해 관리 코드를 호출하려고 하면 액세스 위반이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-105">Access violations occur when attempting to call into managed code through function pointers that were obtained from managed delegates.</span></span> <span data-ttu-id="b92ea-106">이러한 오류는 CLR(공용 언어 런타임) 버그가 아니지만 CLR 코드에서 액세스 위반이 발생하기 때문에 버그처럼 보일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-106">These failures, while not common language runtime (CLR) bugs, may appear to be so because the access violation occurs in the CLR code.</span></span>  
  
 <span data-ttu-id="b92ea-107">오류는 일관성이 없습니다. 함수 포인터에 대한 호출이 성공하는 경우도 있고 실패하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-107">The failure is not consistent; sometimes the call on the function pointer succeeds and sometimes it fails.</span></span> <span data-ttu-id="b92ea-108">부하가 높은 상태에서 또는 임의의 시도 횟수에서만 오류가 발생할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-108">The failure might occur only under heavy load or on a random number of attempts.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b92ea-109">원인</span><span class="sxs-lookup"><span data-stu-id="b92ea-109">Cause</span></span>  
 <span data-ttu-id="b92ea-110">함수 포인터가 생성되고 비관리 코드에 노출된 대리자가 가비지 수집되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-110">The delegate from which the function pointer was created and exposed to unmanaged code was garbage collected.</span></span> <span data-ttu-id="b92ea-111">관리되지 않는 구성 요소가 함수 포인터를 호출하려고 하면 액세스 위반이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-111">When the unmanaged component tries to call on the function pointer, it generates an access violation.</span></span>  
  
 <span data-ttu-id="b92ea-112">가비지 수집이 발생하는 시기에 따라 달라지므로 오류는 무작위인 것처럼 보입니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-112">The failure appears random because it depends on when garbage collection occurs.</span></span> <span data-ttu-id="b92ea-113">대리자가 컬렉션에 적합한 경우 콜백 후에 가비지 수집이 발생할 수 있으며 호출이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-113">If a delegate is eligible for collection, the garbage collection can occur after the callback and the call succeeds.</span></span> <span data-ttu-id="b92ea-114">그러지 않은 경우에는 콜백 전에 가비지 수집이 발생하며, 콜백에서 액세스 위반을 생성하고 프로그램이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-114">At other times, the garbage collection occurs before the callback, the callback generates an access violation, and the program stops.</span></span>  
  
 <span data-ttu-id="b92ea-115">오류 가능성은 대리자 마샬링과 함수 포인터에 대한 콜백 사이의 시간 및 가비지 수집 빈도에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-115">The probability of the failure depends on the time between marshaling the delegate and the callback on the function pointer as well as the frequency of garbage collections.</span></span> <span data-ttu-id="b92ea-116">대리자 마샬링과 이후 콜백 사이의 시간이 짧으면 오류가 드물게 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-116">The failure is sporadic if the time between marshaling the delegate and the ensuing callback is short.</span></span> <span data-ttu-id="b92ea-117">이는 일반적으로 함수 포인터를 받는 관리되지 않는 메서드가 나중에 사용하기 위해 함수 포인터를 저장하지 않고 함수 포인터에 대해 즉시 콜백하여 반환하기 전에 해당 작업을 완료하는 경우에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-117">This is usually the case if the unmanaged method receiving the function pointer does not save the function pointer for later use but instead calls back on the function pointer immediately to complete its operation before returning.</span></span> <span data-ttu-id="b92ea-118">마찬가지로, 시스템의 부하가 높은 상태에서는 가비지 수집이 더 많이 발생하므로 콜백 전에 가비지 수집이 발생할 가능성이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-118">Similarly, more garbage collections occur when a system is under heavy load, which makes it more likely that a garbage collection will occur before the callback.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b92ea-119">해결 방법</span><span class="sxs-lookup"><span data-stu-id="b92ea-119">Resolution</span></span>  
 <span data-ttu-id="b92ea-120">대리자가 관리되지 않는 함수 포인터로 마샬링된 경우 가비지 수집기가 수명을 추적할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-120">Once a delegate has been marshaled out as an unmanaged function pointer, the garbage collector cannot track its lifetime.</span></span> <span data-ttu-id="b92ea-121">대신, 코드에서 관리되지 않는 함수 포인터의 수명 동안 대리자에 대한 참조를 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-121">Instead, your code must keep a reference to the delegate for the lifetime of the unmanaged function pointer.</span></span> <span data-ttu-id="b92ea-122">그러나 이렇게 하려면 먼저 수집된 대리자를 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-122">But before you can do that, you first must identify which delegate was collected.</span></span> <span data-ttu-id="b92ea-123">MDA가 활성화되면 대리자의 형식 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-123">When the MDA is activated, it provides the type name of the delegate.</span></span> <span data-ttu-id="b92ea-124">이 이름을 사용하여 해당 대리자를 비관리 코드에 전달하는 COM 서명이나 플랫폼 호출을 코드에서 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-124">Use this name to search your code for platform invoke or COM signatures that pass that delegate out to unmanaged code.</span></span> <span data-ttu-id="b92ea-125">위반 대리자는 이러한 호출 사이트 중 하나를 통해 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-125">The offending delegate is passed out through one of these call sites.</span></span> <span data-ttu-id="b92ea-126">`gcUnmanagedToManaged` MDA에서 각 런타임 콜백 전에 가비지 수집을 강제할 수 있게 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-126">You can also enable the `gcUnmanagedToManaged` MDA to force a garbage collection before every callback into the runtime.</span></span> <span data-ttu-id="b92ea-127">그러면 항상 콜백 전에 가비지 수집이 발생하므로 가비지 수집에 의한 불확실성이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-127">This will remove the uncertainty introduced by the garbage collection by ensuring that a garbage collection always occurs before the callback.</span></span> <span data-ttu-id="b92ea-128">수집된 대리자를 확인했으면 마샬링된 관리되지 않는 함수 포인터의 수명 동안 관리되는 쪽에서 해당 대리자에 대한 참조를 유지하도록 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-128">Once you know what delegate was collected, change your code to keep a reference to that delegate on the managed side for the lifetime of the marshaled unmanaged function pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b92ea-129">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="b92ea-129">Effect on the Runtime</span></span>  
 <span data-ttu-id="b92ea-130">대리자가 함수 포인터로 마샬링되는 경우 런타임은 비관리에서 관리로 전환을 수행하는 썽크를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-130">When delegates are marshaled as function pointers, the runtime allocates a thunk that does the transition from unmanaged to managed.</span></span> <span data-ttu-id="b92ea-131">이 썽크는 관리되는 대리자가 최종 호출되기 전에 비관리 코드에서 실제로 호출하는 대상입니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-131">This thunk is what the unmanaged code actually calls before the managed delegate is finally invoked.</span></span> <span data-ttu-id="b92ea-132">`callbackOnCollectedDelegate` MDA를 사용할 수 없는 경우 대리자가 수집되면 관리되지 않는 마샬링 코드가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-132">Without the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is deleted when the delegate is collected.</span></span> <span data-ttu-id="b92ea-133">`callbackOnCollectedDelegate` MDA를 사용할 수 있는 경우 대리자가 수집되어도 관리되지 않는 마샬링 코드가 즉시 삭제되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-133">With the `callbackOnCollectedDelegate` MDA enabled, the unmanaged marshaling code is not immediately deleted when the delegate is collected.</span></span> <span data-ttu-id="b92ea-134">대신, 마지막 1,000개 인스턴스가 기본적으로 활성 상태로 유지되고 호출 시 MDA를 활성화하도록 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-134">Instead, the last 1,000 instances are kept alive by default and changed to activate the MDA when called.</span></span> <span data-ttu-id="b92ea-135">썽크는 1,001개 이상의 마샬링된 대리자가 수집된 후에 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-135">The thunk is eventually deleted after 1,001 more marshaled delegates are collected.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b92ea-136">출력</span><span class="sxs-lookup"><span data-stu-id="b92ea-136">Output</span></span>  
 <span data-ttu-id="b92ea-137">MDA는 관리되지 않는 함수 포인터에서 콜백이 시도되기 전에 수집된 대리자의 형식 이름을 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-137">The MDA reports the type name of the delegate that was collected before a callback was attempted on its unmanaged function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b92ea-138">구성</span><span class="sxs-lookup"><span data-stu-id="b92ea-138">Configuration</span></span>  
 <span data-ttu-id="b92ea-139">다음 예제에서는 응용 프로그램 구성 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-139">The following example shows the application configuration options.</span></span> <span data-ttu-id="b92ea-140">MDA에서 활성 상태로 유지하는 썽크 수를 1,500개로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-140">It sets the number of thunks the MDA keeps alive to 1,500.</span></span> <span data-ttu-id="b92ea-141">기본 `listSize` 값은 1,000이고, 최소값은 50이고, 최대값은 2,000입니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-141">The default `listSize` value is 1,000, the minimum is 50, and the maximum is 2,000.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <callbackOnCollectedDelegate listSize="1500" />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="b92ea-142">예</span><span class="sxs-lookup"><span data-stu-id="b92ea-142">Example</span></span>  
 <span data-ttu-id="b92ea-143">다음 예제에서는 이 MDA를 활성화할 수 있는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b92ea-143">The following example demonstrates a situation that can activate this MDA:</span></span>  
  
```  
// Library.cpp : Defines the unmanaged entry point for the DLL application.  
#include "windows.h"  
#include "stdio.h"  
  
void (__stdcall *g_pfTarget)();  
  
void __stdcall Initialize(void __stdcall pfTarget())  
{  
    g_pfTarget = pfTarget;  
}  
  
void __stdcall Callback()  
{  
    g_pfTarget();  
}  
// ---------------------------------------------------  
// C# Client  
using System;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public delegate void DCallback();  
  
    public static void Main()  
    {  
        new Entry();  
        Initialize(Target);  
        GC.Collect();  
        GC.WaitForPendingFinalizers();  
        Callback();  
    }  
  
    public static void Target()  
    {          
    }  
  
    [DllImport("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Initialize(DCallback pfDelegate);  
  
    [DllImport ("Library", CallingConvention = CallingConvention.StdCall)]  
    public static extern void Callback();  
  
    ~Entry() { Console.Error.WriteLine("Entry Collected"); }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b92ea-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b92ea-144">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="b92ea-145">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="b92ea-145">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="b92ea-146">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="b92ea-146">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="b92ea-147">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="b92ea-147">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
