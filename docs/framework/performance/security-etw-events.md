---
title: "보안 ETW 이벤트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abf6e6896267b6d1c8449b020230381923f38f1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="security-etw-events"></a><span data-ttu-id="2fda8-102">보안 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-102">Security ETW Events</span></span>
<a name="top"></a> <span data-ttu-id="2fda8-103">보안 이벤트는 강력한 이름 확인 및 Authenticode 확인 중에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-103">Security events are raised during strong name verification and Authenticode verification.</span></span>  
  
 <span data-ttu-id="2fda8-104">이 범주는 다음 이벤트로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="2fda8-105">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-105">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>](#strongnameverificationstart_v1_and_strongnameverificationstop_v1_events)  
  
-   [<span data-ttu-id="2fda8-106">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-106">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>](#authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events)  
  
<a name="strongnameverificationstart_v1_and_strongnameverificationstop_v1_events"></a>   
## <a name="strongnameverificationstartv1-and-strongnameverificationstopv1-events"></a><span data-ttu-id="2fda8-107">StrongNameVerificationStart_V1 및 StrongNameVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-107">StrongNameVerificationStart_V1 and StrongNameVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="2fda8-108">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="2fda8-109">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2fda8-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="2fda8-110">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="2fda8-110">Keyword for raising the event</span></span>|<span data-ttu-id="2fda8-111">수준</span><span class="sxs-lookup"><span data-stu-id="2fda8-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2fda8-112">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="2fda8-112">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="2fda8-113">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="2fda8-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="2fda8-114">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2fda8-115">이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-115">Event</span></span>|<span data-ttu-id="2fda8-116">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="2fda8-116">Event ID</span></span>|<span data-ttu-id="2fda8-117">발생 시기</span><span class="sxs-lookup"><span data-stu-id="2fda8-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|<span data-ttu-id="2fda8-118">181</span><span class="sxs-lookup"><span data-stu-id="2fda8-118">181</span></span>|<span data-ttu-id="2fda8-119">강력한 이름 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-119">Start of strong name verification.</span></span>|  
|`StrongNameVerificationStop_V1`|<span data-ttu-id="2fda8-120">182</span><span class="sxs-lookup"><span data-stu-id="2fda8-120">182</span></span>|<span data-ttu-id="2fda8-121">강력한 이름 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-121">End of strong name verification.</span></span>|  
  
 <span data-ttu-id="2fda8-122">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-122">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2fda8-123">필드 이름</span><span class="sxs-lookup"><span data-stu-id="2fda8-123">Field name</span></span>|<span data-ttu-id="2fda8-124">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2fda8-124">Data type</span></span>|<span data-ttu-id="2fda8-125">설명</span><span class="sxs-lookup"><span data-stu-id="2fda8-125">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2fda8-126">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="2fda8-126">VerificationFlags</span></span>|<span data-ttu-id="2fda8-127">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2fda8-127">win:UInt32</span></span>|<span data-ttu-id="2fda8-128">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-128">The verification flags.</span></span>|  
|<span data-ttu-id="2fda8-129">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="2fda8-129">ErrorCode</span></span>|<span data-ttu-id="2fda8-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2fda8-130">win:UInt32</span></span>|<span data-ttu-id="2fda8-131">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-131">The HResult error code.</span></span>|  
|<span data-ttu-id="2fda8-132">FullyQualifiedAssemblyName</span><span class="sxs-lookup"><span data-stu-id="2fda8-132">FullyQualifiedAssemblyName</span></span>|<span data-ttu-id="2fda8-133">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2fda8-133">win:UnicodeString</span></span>|<span data-ttu-id="2fda8-134">정규화된 어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-134">The fully qualified assembly name.</span></span>|  
|<span data-ttu-id="2fda8-135">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2fda8-135">ClrInstanceID</span></span>|<span data-ttu-id="2fda8-136">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2fda8-136">win:UInt16</span></span>|<span data-ttu-id="2fda8-137">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-137">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="2fda8-138">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="2fda8-138">Back to top</span></span>](#top)  
  
<a name="authenticodeverificationstart_v1_and_authenticodeverificationstop_v1_events"></a>   
## <a name="authenticodeverificationstartv1-and-authenticodeverificationstopv1-events"></a><span data-ttu-id="2fda8-139">AuthenticodeVerificationStart_V1 및 AuthenticodeVerificationStop_V1 이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-139">AuthenticodeVerificationStart_V1 and AuthenticodeVerificationStop_V1 Events</span></span>  
 <span data-ttu-id="2fda8-140">다음 표에서는 키워드와 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-140">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="2fda8-141">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="2fda8-141">Keyword for raising the event</span></span>|<span data-ttu-id="2fda8-142">수준</span><span class="sxs-lookup"><span data-stu-id="2fda8-142">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="2fda8-143">`SecurityKeyword` (0x400)</span><span class="sxs-lookup"><span data-stu-id="2fda8-143">`SecurityKeyword` (0x400)</span></span>|<span data-ttu-id="2fda8-144">정보 제공(4)</span><span class="sxs-lookup"><span data-stu-id="2fda8-144">Informational(4)</span></span>|  
  
 <span data-ttu-id="2fda8-145">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-145">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="2fda8-146">이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-146">Event</span></span>|<span data-ttu-id="2fda8-147">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="2fda8-147">Event ID</span></span>|<span data-ttu-id="2fda8-148">발생 시기</span><span class="sxs-lookup"><span data-stu-id="2fda8-148">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|<span data-ttu-id="2fda8-149">183</span><span class="sxs-lookup"><span data-stu-id="2fda8-149">183</span></span>|<span data-ttu-id="2fda8-150">Authenticode 확인의 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-150">Start of Authenticode verification.</span></span>|  
|`AuthenticodeVerificationStop_V1`|<span data-ttu-id="2fda8-151">184</span><span class="sxs-lookup"><span data-stu-id="2fda8-151">184</span></span>|<span data-ttu-id="2fda8-152">Authenticode 확인의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-152">End of Authenticode verification.</span></span>|  
  
 <span data-ttu-id="2fda8-153">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-153">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="2fda8-154">필드 이름</span><span class="sxs-lookup"><span data-stu-id="2fda8-154">Field name</span></span>|<span data-ttu-id="2fda8-155">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2fda8-155">Data type</span></span>|<span data-ttu-id="2fda8-156">설명</span><span class="sxs-lookup"><span data-stu-id="2fda8-156">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="2fda8-157">VerificationFlags</span><span class="sxs-lookup"><span data-stu-id="2fda8-157">VerificationFlags</span></span>|<span data-ttu-id="2fda8-158">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2fda8-158">win:UInt32</span></span>|<span data-ttu-id="2fda8-159">확인 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-159">The verification flags.</span></span>|  
|<span data-ttu-id="2fda8-160">ErrorCode</span><span class="sxs-lookup"><span data-stu-id="2fda8-160">ErrorCode</span></span>|<span data-ttu-id="2fda8-161">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="2fda8-161">win:UInt32</span></span>|<span data-ttu-id="2fda8-162">HResult 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-162">The HResult error code.</span></span>|  
|<span data-ttu-id="2fda8-163">ModulePath</span><span class="sxs-lookup"><span data-stu-id="2fda8-163">ModulePath</span></span>|<span data-ttu-id="2fda8-164">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="2fda8-164">win:UnicodeString</span></span>|<span data-ttu-id="2fda8-165">모듈 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-165">The module path.</span></span>|  
|<span data-ttu-id="2fda8-166">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="2fda8-166">ClrInstanceID</span></span>|<span data-ttu-id="2fda8-167">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="2fda8-167">win:UInt16</span></span>|<span data-ttu-id="2fda8-168">CLR 또는 CoreCLR 인스턴스에 대한 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2fda8-168">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fda8-169">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fda8-169">See Also</span></span>  
 [<span data-ttu-id="2fda8-170">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="2fda8-170">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
