---
title: overlappedFreeError MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 645c9f6c5a2a693fb2b88b2b2bc1c40501eecde8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="5c702-102">overlappedFreeError MDA</span><span class="sxs-lookup"><span data-stu-id="5c702-102">overlappedFreeError MDA</span></span>
<span data-ttu-id="5c702-103">`overlappedFreeError` MDA(관리 디버깅 도우미)는 겹치는 작업이 완료되기 전에 <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> 메서드를 호출하면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-103">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5c702-104">증상</span><span class="sxs-lookup"><span data-stu-id="5c702-104">Symptoms</span></span>  
 <span data-ttu-id="5c702-105">액세스 위반 또는 가비지 수집된 힙의 손상입니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-105">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5c702-106">원인</span><span class="sxs-lookup"><span data-stu-id="5c702-106">Cause</span></span>  
 <span data-ttu-id="5c702-107">작업이 완료되기 전에 겹친 구조체가 해제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-107">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="5c702-108">겹친 포인터를 사용하는 함수는 나중에 해제된 후 구조체에 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-108">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="5c702-109">따라서 다른 개체가 현재 해당 지역을 사용하고 있을 수 있으므로 힙이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-109">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="5c702-110">겹친 작업이 성공적으로 시작하지 않은 경우 이 MDA는 오류를 나타내지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-110">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5c702-111">해결</span><span class="sxs-lookup"><span data-stu-id="5c702-111">Resolution</span></span>  
 <span data-ttu-id="5c702-112"><xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> 메서드를 호출하기 전에 겹친 구조체를 사용하는 I/O 작업이 완료되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-112">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5c702-113">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="5c702-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="5c702-114">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5c702-115">출력</span><span class="sxs-lookup"><span data-stu-id="5c702-115">Output</span></span>  
 <span data-ttu-id="5c702-116">다음은 이 MDA의 샘플 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="5c702-116">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="5c702-117">구성</span><span class="sxs-lookup"><span data-stu-id="5c702-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c702-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5c702-118">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="5c702-119">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="5c702-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="5c702-120">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="5c702-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
