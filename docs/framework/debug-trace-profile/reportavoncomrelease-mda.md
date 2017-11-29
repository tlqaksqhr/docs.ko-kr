---
title: reportAvOnComRelease MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: de48fca818f8456627c9507756cc2d8a200c50e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="de945-102">reportAvOnComRelease MDA</span><span class="sxs-lookup"><span data-stu-id="de945-102">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="de945-103">`reportAvOnComRelease` MDA(관리 디버깅 도우미)는 COM interop를 수행하고 원시 COM 호출과 결합된 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 또는 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 메서드를 사용하는 동안 사용자 참조 계산 오류로 인해 예외가 throw되면 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="de945-103">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="de945-104">증상</span><span class="sxs-lookup"><span data-stu-id="de945-104">Symptoms</span></span>  
 <span data-ttu-id="de945-105">액세스 위반 및 메모리 손상이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="de945-105">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="de945-106">원인</span><span class="sxs-lookup"><span data-stu-id="de945-106">Cause</span></span>  
 <span data-ttu-id="de945-107">경우에 따라, COM interop를 수행하고 원시 COM 호출과 결합된 <xref:System.Runtime.InteropServices.Marshal.Release%2A> 또는 <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> 메서드를 사용하는 동안 사용자 참조 계산 오류로 인해 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="de945-107">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="de945-108">일반적으로 이 예외는 이렇게 하지 않으면 CLR에서 액세스 위반이 발생하여 CLR이 종료되기 때문에 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="de945-108">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="de945-109">이 도우미를 사용하도록 설정한 경우 이러한 예외는 단순히 무시되는 것이 아니라 감지 및 보고될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de945-109">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="de945-110">해결 방법</span><span class="sxs-lookup"><span data-stu-id="de945-110">Resolution</span></span>  
 <span data-ttu-id="de945-111">참조 계산 코드를 검토하고 오류를 검색하며, 개체의 네이티브 클라이언트에 참조 계산 오류가 있는지 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="de945-111">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="de945-112">런타임에 대한 영향</span><span class="sxs-lookup"><span data-stu-id="de945-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="de945-113">두 가지 모드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de945-113">Two modes are available.</span></span> <span data-ttu-id="de945-114">`allowAv` 특성이 `true`인 경우 도우미가 런타임에서 액세스 위반을 무시하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="de945-114">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="de945-115">`allowAv`가 `false`(기본값)인 경우 런타임에서 액세스 위반을 무시하지만 예외가 throw 및 무시되었음을 나타내는 경고 메시지가 사용자에게 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="de945-115">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="de945-116">출력</span><span class="sxs-lookup"><span data-stu-id="de945-116">Output</span></span>  
 <span data-ttu-id="de945-117">가능한 경우 출력에 COM 인터페이스 포인터의 원래 vtable이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="de945-117">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="de945-118">그러지 않으면 정보 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="de945-118">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="de945-119">구성</span><span class="sxs-lookup"><span data-stu-id="de945-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="de945-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de945-120">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="de945-121">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="de945-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="de945-122">interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="de945-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
