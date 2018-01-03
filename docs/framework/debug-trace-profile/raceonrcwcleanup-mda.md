---
title: raceOnRCWCleanup MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33d1c7d91c33c194353af43deed9329b9b4ec841
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="06b9e-102">raceOnRCWCleanup MDA</span><span class="sxs-lookup"><span data-stu-id="06b9e-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="06b9e-103">`raceOnRCWCleanup` MDA(관리 디버깅 도우미)는 CLR(공용 언어 런타임)에서 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> 메서드와 같은 명령을 사용하여 해제 호출을 수행할 때 RCW( [런타임 호출 가능 래퍼](../../../docs/framework/interop/runtime-callable-wrapper.md))가 사용 중임을 발견할 경우 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="06b9e-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="06b9e-104">증상</span><span class="sxs-lookup"><span data-stu-id="06b9e-104">Symptoms</span></span>  
 <span data-ttu-id="06b9e-105"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 또는 이와 비슷한 메서드를 사용하여 RCW를 해제하는 중이나 그 이후에 액세스 위반 또는 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="06b9e-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="06b9e-106">원인</span><span class="sxs-lookup"><span data-stu-id="06b9e-106">Cause</span></span>  
 <span data-ttu-id="06b9e-107">RCW가 다른 스레드나 해제 스레드 스택에서 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="06b9e-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="06b9e-108">사용 중인 RCW는 해제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06b9e-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="06b9e-109">해결</span><span class="sxs-lookup"><span data-stu-id="06b9e-109">Resolution</span></span>  
 <span data-ttu-id="06b9e-110">현재 스레드나 다른 스레드에서 사용 중일 수 있는 RCW는 해제하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="06b9e-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="06b9e-111">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="06b9e-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="06b9e-112">이 MDA는 CLR에 아무런 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06b9e-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="06b9e-113">출력</span><span class="sxs-lookup"><span data-stu-id="06b9e-113">Output</span></span>  
 <span data-ttu-id="06b9e-114">오류를 설명하는 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="06b9e-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="06b9e-115">구성</span><span class="sxs-lookup"><span data-stu-id="06b9e-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="06b9e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06b9e-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="06b9e-117">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="06b9e-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="06b9e-118">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="06b9e-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
