---
title: "Interop ETW 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5670eb910406626096f776d3b4192e2d58d7ce1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="71cbe-102">Interop ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-102">Interop ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="71cbe-103">Interop 이벤트는 MSIL(Microsoft Intermediate Language) 스텁 생성 및 캐싱에 대한 정보를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-103">Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="71cbe-104">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="71cbe-105">ILStubGenerated 이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="71cbe-106">ILStubCacheHit 이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="71cbe-107">ILStubGenerated 이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="71cbe-108">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="71cbe-109">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71cbe-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="71cbe-110">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="71cbe-110">Keyword for raising the event</span></span>|<span data-ttu-id="71cbe-111">수준</span><span class="sxs-lookup"><span data-stu-id="71cbe-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71cbe-112">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="71cbe-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="71cbe-113">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="71cbe-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="71cbe-114">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71cbe-115">이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-115">Event</span></span>|<span data-ttu-id="71cbe-116">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="71cbe-116">Event ID</span></span>|<span data-ttu-id="71cbe-117">발생 시기</span><span class="sxs-lookup"><span data-stu-id="71cbe-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="71cbe-118">88</span><span class="sxs-lookup"><span data-stu-id="71cbe-118">88</span></span>|<span data-ttu-id="71cbe-119">MSIL 스텁이 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="71cbe-120">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71cbe-121">필드 이름</span><span class="sxs-lookup"><span data-stu-id="71cbe-121">Field name</span></span>|<span data-ttu-id="71cbe-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="71cbe-122">Data type</span></span>|<span data-ttu-id="71cbe-123">설명</span><span class="sxs-lookup"><span data-stu-id="71cbe-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71cbe-124">ModuleID</span><span class="sxs-lookup"><span data-stu-id="71cbe-124">ModuleID</span></span>|<span data-ttu-id="71cbe-125">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71cbe-125">win:UInt16</span></span>|<span data-ttu-id="71cbe-126">모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-126">The module identifier.</span></span>|  
|<span data-ttu-id="71cbe-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="71cbe-127">StubMethodID</span></span>|<span data-ttu-id="71cbe-128">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71cbe-128">win:UInt64</span></span>|<span data-ttu-id="71cbe-129">스텁 메서드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="71cbe-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="71cbe-130">StubFlags</span></span>|<span data-ttu-id="71cbe-131">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71cbe-131">win:UInt64</span></span>|<span data-ttu-id="71cbe-132">스텁에 대한 플래그:</span><span class="sxs-lookup"><span data-stu-id="71cbe-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="71cbe-133">0x1 - 역방향 interop</span><span class="sxs-lookup"><span data-stu-id="71cbe-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="71cbe-134">0x2 - COM interop</span><span class="sxs-lookup"><span data-stu-id="71cbe-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="71cbe-135">0x4 - NGen.exe에서 생성한 스텁</span><span class="sxs-lookup"><span data-stu-id="71cbe-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="71cbe-136">0x8 - 대리자</span><span class="sxs-lookup"><span data-stu-id="71cbe-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="71cbe-137">0x10 - 가변 인수</span><span class="sxs-lookup"><span data-stu-id="71cbe-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="71cbe-138">0x20 - 비관리 호출 수신자</span><span class="sxs-lookup"><span data-stu-id="71cbe-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="71cbe-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="71cbe-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="71cbe-140">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71cbe-140">win:UInt32</span></span>|<span data-ttu-id="71cbe-141">관리되는 interop 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="71cbe-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="71cbe-143">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-143">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-144">관리되는 interop 메서드의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="71cbe-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="71cbe-146">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-146">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-147">관리되는 interop 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="71cbe-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="71cbe-149">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-149">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-150">관리되는 interop 메서드의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="71cbe-151">NativeMethodSignature</span></span>|<span data-ttu-id="71cbe-152">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-152">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-153">네이티브 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-153">The native method signature.</span></span>|  
|<span data-ttu-id="71cbe-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="71cbe-154">StubMethodSignature</span></span>|<span data-ttu-id="71cbe-155">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-155">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-156">스텁 메서드 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-156">The stub method signature.</span></span>|  
|<span data-ttu-id="71cbe-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="71cbe-157">StubMethodILCode</span></span>|<span data-ttu-id="71cbe-158">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-158">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-159">스텁 메서드의 MSIL 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="71cbe-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71cbe-160">ClrInstanceID</span></span>|<span data-ttu-id="71cbe-161">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71cbe-161">win:UInt16</span></span>|<span data-ttu-id="71cbe-162">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71cbe-163">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="71cbe-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="71cbe-164">ILStubCacheHit 이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="71cbe-165">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="71cbe-166">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="71cbe-166">Keyword for raising the event</span></span>|<span data-ttu-id="71cbe-167">수준</span><span class="sxs-lookup"><span data-stu-id="71cbe-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="71cbe-168">`InteropKeyword` (0x2000)</span><span class="sxs-lookup"><span data-stu-id="71cbe-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="71cbe-169">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="71cbe-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="71cbe-170">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="71cbe-171">이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-171">Event</span></span>|<span data-ttu-id="71cbe-172">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="71cbe-172">Event ID</span></span>|<span data-ttu-id="71cbe-173">발생 시기</span><span class="sxs-lookup"><span data-stu-id="71cbe-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="71cbe-174">89</span><span class="sxs-lookup"><span data-stu-id="71cbe-174">89</span></span>|<span data-ttu-id="71cbe-175">MSIL 캐시가 액세스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="71cbe-176">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="71cbe-177">필드 이름</span><span class="sxs-lookup"><span data-stu-id="71cbe-177">Field name</span></span>|<span data-ttu-id="71cbe-178">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="71cbe-178">Data type</span></span>|<span data-ttu-id="71cbe-179">설명</span><span class="sxs-lookup"><span data-stu-id="71cbe-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="71cbe-180">ModuleID</span><span class="sxs-lookup"><span data-stu-id="71cbe-180">ModuleID</span></span>|<span data-ttu-id="71cbe-181">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71cbe-181">win:UInt16</span></span>|<span data-ttu-id="71cbe-182">모듈 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-182">The module identifier.</span></span>|  
|<span data-ttu-id="71cbe-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="71cbe-183">StubMethodID</span></span>|<span data-ttu-id="71cbe-184">win:UInt64</span><span class="sxs-lookup"><span data-stu-id="71cbe-184">win:UInt64</span></span>|<span data-ttu-id="71cbe-185">스텁 메서드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="71cbe-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="71cbe-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="71cbe-187">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="71cbe-187">win:UInt32</span></span>|<span data-ttu-id="71cbe-188">관리되는 interop 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="71cbe-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="71cbe-190">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-190">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-191">관리되는 interop 메서드의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="71cbe-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="71cbe-193">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-193">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-194">관리되는 interop 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="71cbe-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="71cbe-196">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="71cbe-196">win:UnicodeString</span></span>|<span data-ttu-id="71cbe-197">관리되는 interop 메서드의 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="71cbe-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="71cbe-198">ClrInstanceID</span></span>|<span data-ttu-id="71cbe-199">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="71cbe-199">win:UInt16</span></span>|<span data-ttu-id="71cbe-200">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="71cbe-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="71cbe-201">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="71cbe-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="71cbe-202">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71cbe-202">See Also</span></span>  
 [<span data-ttu-id="71cbe-203">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="71cbe-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
