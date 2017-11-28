---
title: "Interop 마샬링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- marshaling, COM interop
- interop marshaling
- interop marshaling, about interop marshaling
ms.assetid: 115f7a2f-d422-4605-ab36-13a8dd28142a
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 381eccc42d5abb85cde618f4710f044f172295d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="interop-marshaling"></a><span data-ttu-id="2b0a1-102">Interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-102">Interop Marshaling</span></span>
<span data-ttu-id="2b0a1-103"><a name="top"></a> Interop 마샬링은 호출 중 관리되는 메모리와 관리되지 않는 메모리 간에 메서드 인수와 반환 값을 통해 데이터를 전달하는 방법을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-103"><a name="top"></a> Interop marshaling governs how data is passed in method arguments and return values between managed and unmanaged memory during calls.</span></span> <span data-ttu-id="2b0a1-104">Interop 마샬링은 공용 언어 런타임 마샬링 서비스에서 수행하는 런타임 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-104">Interop marshaling is a run-time activity performed by the common language runtime's marshaling service.</span></span>  
  
 <span data-ttu-id="2b0a1-105">대부분의 데이터 형식은 관리되는 메모리와 관리되지 않는 메모리 둘 다에서 공통된 표현을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-105">Most data types have common representations in both managed and unmanaged memory.</span></span> <span data-ttu-id="2b0a1-106">Interop 마샬러는 이러한 형식을 자동으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-106">The interop marshaler handles these types for you.</span></span> <span data-ttu-id="2b0a1-107">다른 형식은 모호하거나 관리되는 메모리에서 표시되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-107">Other types can be ambiguous or not represented at all in managed memory.</span></span>  
  
 <span data-ttu-id="2b0a1-108">모호한 형식은 관리되는 단일 형식에 관리되지 않는 여러 표현이 매핑되거나 배열 크기와 같은 형식 정보가 누락되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-108">An ambiguous type can have either multiple unmanaged representations that map to a single managed type, or missing type information, such as the size of an array.</span></span> <span data-ttu-id="2b0a1-109">모호한 형식에 대해 마샬러는 기본 표현과 여러 표현이 있는 대체 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-109">For ambiguous types, the marshaler provides a default representation and alternative representations where multiple representations exist.</span></span> <span data-ttu-id="2b0a1-110">모호한 형식을 마샬링하는 방법에 대한 명시적 지침을 마샬러에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-110">You can supply explicit instructions to the marshaler on how it is to marshal an ambiguous type.</span></span>  
  
 <span data-ttu-id="2b0a1-111">이 개요는 다음과 같은 단원으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-111">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="2b0a1-112">플랫폼 호출 및 COM Interop 모델</span><span class="sxs-lookup"><span data-stu-id="2b0a1-112">Platform Invoke and COM Interop Models</span></span>](#platform_invoke_and_com_interop_models)  
  
-   [<span data-ttu-id="2b0a1-113">마샬링 및 COM 아파트</span><span class="sxs-lookup"><span data-stu-id="2b0a1-113">Marshaling and COM Apartments</span></span>](#marshaling_and_com_apartments)  
  
-   [<span data-ttu-id="2b0a1-114">원격 호출 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-114">Marshaling Remote Calls</span></span>](#marshaling_remote_calls)  
  
-   [<span data-ttu-id="2b0a1-115">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2b0a1-115">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="2b0a1-116">참조</span><span class="sxs-lookup"><span data-stu-id="2b0a1-116">Reference</span></span>](#reference)  
  
<a name="platform_invoke_and_com_interop_models"></a>   
## <a name="platform-invoke-and-com-interop-models"></a><span data-ttu-id="2b0a1-117">플랫폼 호출 및 COM Interop 모델</span><span class="sxs-lookup"><span data-stu-id="2b0a1-117">Platform Invoke and COM Interop Models</span></span>  
 <span data-ttu-id="2b0a1-118">공용 언어 런타임은 비관리 코드와 상호 운용하는 두 가지 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-118">The common language runtime provides two mechanisms for interoperating with unmanaged code:</span></span>  
  
-   <span data-ttu-id="2b0a1-119">플랫폼 호출 - 관리 코드가 관리되지 않는 라이브러리에서 내보낸 함수를 호출할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-119">Platform invoke, which enables managed code to call functions exported from an unmanaged library.</span></span>  
  
-   <span data-ttu-id="2b0a1-120">COM interop - 관리 코드가 인터페이스를 통해 COM(구성 요소 개체 모델) 개체와 상호 운용할 수 있게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-120">COM interop, which enables managed code to interact with Component Object Model (COM) objects through interfaces.</span></span>  
  
 <span data-ttu-id="2b0a1-121">플랫폼 호출과 COM interop는 둘 다 interop 마샬링을 사용하여 호출자와 호출 수신자 간에 메서드 인수를 정확하게 이동하고 필요한 경우 역방향으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-121">Both platform invoke and COM interop use interop marshaling to accurately move method arguments between caller and callee and back, if required.</span></span> <span data-ttu-id="2b0a1-122">다음 그림과 같이 플랫폼 호출 메서드는 관리 코드에서 비관리 코드로 전달되며 [콜백 함수](../../../docs/framework/interop/callback-functions.md)가 사용되는 경우를 제외하고 반대 방향으로 전달되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-122">As the following illustration shows, a platform invoke method call flows from managed to unmanaged code and never the other way, except when [callback functions](../../../docs/framework/interop/callback-functions.md) are involved.</span></span> <span data-ttu-id="2b0a1-123">플랫폼 호출은 관리 코드에서 비관리 코드로만 전달될 수 있지만 데이터는 입력 또는 출력 매개 변수로 양방향으로 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-123">Even though platform invoke calls can flow only from managed to unmanaged code, data can flow in both directions as input or output parameters.</span></span> <span data-ttu-id="2b0a1-124">COM interop 메서드 호출은 어느 방향으로든 전달될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-124">COM interop method calls can flow in either direction.</span></span>  
  
 <span data-ttu-id="2b0a1-125">![플랫폼 호출](../../../docs/framework/interop/media/interopmarshaling.png "interopmarshaling")</span><span class="sxs-lookup"><span data-stu-id="2b0a1-125">![Platform invoke](../../../docs/framework/interop/media/interopmarshaling.png "interopmarshaling")</span></span>  
<span data-ttu-id="2b0a1-126">플랫폼 호출 및 COM Interop 호출 흐름</span><span class="sxs-lookup"><span data-stu-id="2b0a1-126">Platform invoke and COM interop call flow</span></span>  
  
 <span data-ttu-id="2b0a1-127">가장 낮은 수준에서 두 메커니즘은 모두 동일한 interop 마샬링 서비스를 사용하지만 특정 데이터 형식은 COM interop 또는 플랫폼 호출에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-127">At the lowest level, both mechanisms use the same interop marshaling service; however, certain data types are supported exclusively by COM interop or platform invoke.</span></span> <span data-ttu-id="2b0a1-128">자세한 내용은 [기본 마샬링 동작](../../../docs/framework/interop/default-marshaling-behavior.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-128">For details, see [Default Marshaling Behavior](../../../docs/framework/interop/default-marshaling-behavior.md).</span></span>  
  
 [<span data-ttu-id="2b0a1-129">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="2b0a1-129">Back to top</span></span>](#top)  
  
<a name="marshaling_and_com_apartments"></a>   
## <a name="marshaling-and-com-apartments"></a><span data-ttu-id="2b0a1-130">마샬링 및 COM 아파트</span><span class="sxs-lookup"><span data-stu-id="2b0a1-130">Marshaling and COM Apartments</span></span>  
 <span data-ttu-id="2b0a1-131">interop 마샬러는 공용 언어 런타임 힙과 관리되지 않는 힙 간에 데이터를 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-131">The interop marshaler marshals data between the common language runtime heap and the unmanaged heap.</span></span> <span data-ttu-id="2b0a1-132">호출자와 호출 수신자가 동일한 데이터 인스턴스에서 작동할 수 없을 때마다 마샬링이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-132">Marshaling occurs whenever the caller and callee cannot operate on the same instance of data.</span></span> <span data-ttu-id="2b0a1-133">interop 마샬러를 사용하면 호출자와 호출 수신자가 고유한 데이터 복사본이 있는 것처럼 동일한 데이터에서 작동하는 것으로 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-133">The interop marshaler makes it possible for the caller and callee to appear to be operating on the same data even if they have their own copy of the data.</span></span>  
  
 <span data-ttu-id="2b0a1-134">COM에는 COM 아파트 간이나 서로 다른 COM 프로세스 간에 데이터를 마샬링하는 마샬러도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-134">COM also has a marshaler that marshals data between COM apartments or different COM processes.</span></span> <span data-ttu-id="2b0a1-135">동일한 COM 아파트 내의 관리 코드와 비관리 코드 간에 호출하는 경우에는 interop 마샬러만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-135">When calling between managed and unmanaged code within the same COM apartment, the interop marshaler is the only marshaler involved.</span></span> <span data-ttu-id="2b0a1-136">다른 COM 아파트나 다른 프로세스 내의 관리 코드와 비관리 코드 간에 호출하는 경우 interop 마샬러와 COM 마샬러가 모두 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-136">When calling between managed code and unmanaged code in a different COM apartment or a different process, both the interop marshaler and the COM marshaler are involved.</span></span>  
  
### <a name="com-clients-and-managed-servers"></a><span data-ttu-id="2b0a1-137">COM 클라이언트 및 관리되는 서버</span><span class="sxs-lookup"><span data-stu-id="2b0a1-137">COM Clients and Managed Servers</span></span>  
 <span data-ttu-id="2b0a1-138">[Regasm.exe(어셈블리 등록 도구)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)로 등록된 형식 라이브러리를 사용하여 내보낸 관리되는 서버는 `ThreadingModel` 레지스트리 항목이 `Both`로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-138">An exported managed server with a type library registered by the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) has a `ThreadingModel` registry entry set to `Both`.</span></span> <span data-ttu-id="2b0a1-139">이 값은 STA(단일 스레드 아파트) 또는 MTA(다중 스레드 아파트)로 서버를 활성화할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-139">This value indicates that the server can be activated in a single-threaded apartment (STA) or a multithreaded apartment (MTA).</span></span> <span data-ttu-id="2b0a1-140">서버 개체는 다음 표와 같이 해당 호출자와 동일한 아파트에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-140">The server object is created in the same apartment as its caller, as shown in the following table.</span></span>  
  
|<span data-ttu-id="2b0a1-141">COM 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2b0a1-141">COM client</span></span>|<span data-ttu-id="2b0a1-142">.NET 서버</span><span class="sxs-lookup"><span data-stu-id="2b0a1-142">.NET server</span></span>|<span data-ttu-id="2b0a1-143">마샬링 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b0a1-143">Marshaling requirements</span></span>|  
|----------------|-----------------|-----------------------------|  
|<span data-ttu-id="2b0a1-144">STA</span><span class="sxs-lookup"><span data-stu-id="2b0a1-144">STA</span></span>|<span data-ttu-id="2b0a1-145">`Both`가 STA로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-145">`Both` becomes STA.</span></span>|<span data-ttu-id="2b0a1-146">동일한 아파트 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-146">Same-apartment marshaling.</span></span>|  
|<span data-ttu-id="2b0a1-147">MTA</span><span class="sxs-lookup"><span data-stu-id="2b0a1-147">MTA</span></span>|<span data-ttu-id="2b0a1-148">`Both`가 MTA로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-148">`Both` becomes MTA.</span></span>|<span data-ttu-id="2b0a1-149">동일한 아파트 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-149">Same-apartment marshaling.</span></span>|  
  
 <span data-ttu-id="2b0a1-150">클라이언트와 서버가 동일한 아파트에 있으므로 interop 마샬링 서비스에서 모든 데이터 마샬링을 자동으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-150">Because the client and server are in the same apartment, the interop marshaling service automatically handles all data marshaling.</span></span> <span data-ttu-id="2b0a1-151">다음 그림에서는 동일한 COM 스타일 아파트 내의 관리되는 힙과 관리되지 않는 힙 간에 작동하는 interop 마샬링 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-151">The following illustration shows the interop marshaling service operating between managed and unmanaged heaps within the same COM-style apartment.</span></span>  
  
 <span data-ttu-id="2b0a1-152">![interop 마샬링](../../../docs/framework/interop/media/interopheap.gif "interopheap")</span><span class="sxs-lookup"><span data-stu-id="2b0a1-152">![Interop marshaling](../../../docs/framework/interop/media/interopheap.gif "interopheap")</span></span>  
<span data-ttu-id="2b0a1-153">동일한 아파트 마샬링 프로세스</span><span class="sxs-lookup"><span data-stu-id="2b0a1-153">Same-apartment marshaling process</span></span>  
  
 <span data-ttu-id="2b0a1-154">관리되는 서버를 내보내려는 경우 COM 클라이언트가 서버의 아파트를 결정하는 것에 주의합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-154">If you plan to export a managed server, be aware that the COM client determines the apartment of the server.</span></span> <span data-ttu-id="2b0a1-155">MTA로 초기화된 COM 클라이언트에서 호출하는 관리되는 서버는 스레드로부터 안전해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-155">A managed server called by a COM client initialized in an MTA must ensure thread safety.</span></span>  
  
### <a name="managed-clients-and-com-servers"></a><span data-ttu-id="2b0a1-156">관리되는 클라이언트 및 COM 서버</span><span class="sxs-lookup"><span data-stu-id="2b0a1-156">Managed Clients and COM Servers</span></span>  
 <span data-ttu-id="2b0a1-157">관리되는 클라이언트 아파트에 대한 기본 설정은 MTA입니다. 그러나 .NET 클라이언트의 응용 프로그램 형식을 통해 기본 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-157">The default setting for managed client apartments is MTA; however, the application type of the .NET client can change the default setting.</span></span> <span data-ttu-id="2b0a1-158">예를 들어 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 클라이언트 아파트 설정은 STA입니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-158">For example, a [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] client apartment setting is STA.</span></span> <span data-ttu-id="2b0a1-159"><xref:System.STAThreadAttribute?displayProperty=nameWithType>, <xref:System.MTAThreadAttribute?displayProperty=nameWithType>, <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> 속성 또는 <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> 속성을 사용하여 관리되는 클라이언트의 아파트 설정을 검사하고 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-159">You can use the <xref:System.STAThreadAttribute?displayProperty=nameWithType>, the <xref:System.MTAThreadAttribute?displayProperty=nameWithType>, the <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType> property, or the <xref:System.Web.UI.Page.AspCompatMode%2A?displayProperty=nameWithType> property to examine and change the apartment setting of a managed client.</span></span>  
  
 <span data-ttu-id="2b0a1-160">구성 요소의 작성자가 COM 서버의 스레드 선호도를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-160">The author of the component sets the thread affinity of a COM server.</span></span> <span data-ttu-id="2b0a1-161">다음 표에서는 .NET 클라이언트 및 COM 서버에 대한 아파트 설정의 조합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-161">The following table shows the combinations of apartment settings for .NET clients and COM servers.</span></span> <span data-ttu-id="2b0a1-162">또한 조합에 대한 마샬링 요구 사항을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-162">It also shows the resulting marshaling requirements for the combinations.</span></span>  
  
|<span data-ttu-id="2b0a1-163">.NET 클라이언트</span><span class="sxs-lookup"><span data-stu-id="2b0a1-163">.NET client</span></span>|<span data-ttu-id="2b0a1-164">COM 서버</span><span class="sxs-lookup"><span data-stu-id="2b0a1-164">COM server</span></span>|<span data-ttu-id="2b0a1-165">마샬링 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b0a1-165">Marshaling requirements</span></span>|  
|-----------------|----------------|-----------------------------|  
|<span data-ttu-id="2b0a1-166">MTA(기본값)</span><span class="sxs-lookup"><span data-stu-id="2b0a1-166">MTA (default)</span></span>|<span data-ttu-id="2b0a1-167">MTA</span><span class="sxs-lookup"><span data-stu-id="2b0a1-167">MTA</span></span><br /><br /> <span data-ttu-id="2b0a1-168">STA</span><span class="sxs-lookup"><span data-stu-id="2b0a1-168">STA</span></span>|<span data-ttu-id="2b0a1-169">Interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-169">Interop marshaling.</span></span><br /><br /> <span data-ttu-id="2b0a1-170">Interop 및 COM 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-170">Interop and COM marshaling.</span></span>|  
|<span data-ttu-id="2b0a1-171">STA</span><span class="sxs-lookup"><span data-stu-id="2b0a1-171">STA</span></span>|<span data-ttu-id="2b0a1-172">MTA</span><span class="sxs-lookup"><span data-stu-id="2b0a1-172">MTA</span></span><br /><br /> <span data-ttu-id="2b0a1-173">STA</span><span class="sxs-lookup"><span data-stu-id="2b0a1-173">STA</span></span>|<span data-ttu-id="2b0a1-174">Interop 및 COM 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-174">Interop and COM marshaling.</span></span><br /><br /> <span data-ttu-id="2b0a1-175">Interop 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-175">Interop marshaling.</span></span>|  
  
 <span data-ttu-id="2b0a1-176">관리되는 클라이언트와 관리되지 않는 서버가 동일한 아파트에 있으므로 interop 마샬링 서비스에서 모든 데이터 마샬링을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-176">When a managed client and unmanaged server are in the same apartment, the interop marshaling service handles all data marshaling.</span></span> <span data-ttu-id="2b0a1-177">그러나 클라이언트와 서버가 서로 다른 아파트에서 초기화된 경우 COM 마샬링도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-177">However, when client and server are initialized in different apartments, COM marshaling is also required.</span></span> <span data-ttu-id="2b0a1-178">다음 그림에서는 아파트 간 호출의 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-178">The following illustration shows the elements of a cross-apartment call.</span></span>  
  
 <span data-ttu-id="2b0a1-179">![COM 마샬링](../../../docs/framework/interop/media/singleprocessmultapt.gif "singleprocessmultapt")</span><span class="sxs-lookup"><span data-stu-id="2b0a1-179">![COM marshaling](../../../docs/framework/interop/media/singleprocessmultapt.gif "singleprocessmultapt")</span></span>  
<span data-ttu-id="2b0a1-180">.NET 클라이언트와 COM 개체 간의 아파트 간 호출</span><span class="sxs-lookup"><span data-stu-id="2b0a1-180">Cross-apartment call between a .NET client and COM object</span></span>  
  
 <span data-ttu-id="2b0a1-181">아파트 간 마샬링의 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-181">For cross-apartment marshaling, you can do the following:</span></span>  
  
-   <span data-ttu-id="2b0a1-182">경계를 넘어가는 호출이 많은 경우에만 두드러지는 아파트 간 마샬링의 오버헤드를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-182">Accept the overhead of the cross-apartment marshaling, which is noticeable only when there are many calls across the boundary.</span></span> <span data-ttu-id="2b0a1-183">호출이 성공적으로 아파트 경계를 넘어가려면 COM 구성 요소의 형식 라이브러리를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-183">You must register the type library of the COM component for calls to successfully cross the apartment boundary.</span></span>  
  
-   <span data-ttu-id="2b0a1-184">클라이언트 스레드를 STA 또는 MTA로 설정하여 주 스레드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-184">Alter the main thread by setting the client thread to STA or MTA.</span></span> <span data-ttu-id="2b0a1-185">예를 들어 C# 클라이언트가 많은 STA COM 구성 요소를 호출하는 경우 주 스레드를 STA로 설정하여 아파트 간 마샬링을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-185">For example, if your C# client calls many STA COM components, you can avoid cross-apartment marshaling by setting the main thread to STA.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b0a1-186">C# 클라이언트의 스레드를 STA로 설정한 후 MTA COM 구성 요소를 호출하려면 아파트 간 마샬링이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-186">Once the thread of a C# client is set to STA, calls to MTA COM components will require cross-apartment marshaling.</span></span>  
  
 <span data-ttu-id="2b0a1-187">아파트 모델을 명시적으로 선택하는 방법에 대한 자세한 내용은 [관리되는 스레딩과 관리되지 않는 스레딩](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-187">For instructions on explicitly selecting an apartment model, see [Managed and Unmanaged Threading](http://msdn.microsoft.com/en-us/db425c20-4b2f-4433-bf96-76071c7881e5).</span></span>  
  
 [<span data-ttu-id="2b0a1-188">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="2b0a1-188">Back to top</span></span>](#top)  
  
<a name="marshaling_remote_calls"></a>   
## <a name="marshaling-remote-calls"></a><span data-ttu-id="2b0a1-189">원격 호출 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-189">Marshaling Remote Calls</span></span>  
 <span data-ttu-id="2b0a1-190">아파트 간 마샬링과 마찬가지로 COM 마샬링은 개체가 개별 프로세스에 상주할 때마다 관리 및 비관리 코드 간의 각 호출에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-190">As with cross-apartment marshaling, COM marshaling is involved in each call between managed and unmanaged code whenever the objects reside in separate processes.</span></span> <span data-ttu-id="2b0a1-191">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-191">For example:</span></span>  
  
-   <span data-ttu-id="2b0a1-192">원격 호스트의 관리되는 서버를 호출하는 COM 클라이언트는 DCOM(분산된 COM)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-192">A COM client that invokes a managed server on a remote host uses distributed COM (DCOM).</span></span>  
  
-   <span data-ttu-id="2b0a1-193">원격 호스트의 COM 서버를 호출하는 관리되는 클라이언트는 DCOM을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-193">A managed client that invokes a COM server on a remote host uses DCOM.</span></span>  
  
 <span data-ttu-id="2b0a1-194">다음 그림에서는 interop 마샬링과 COM 마샬링이 프로세스 및 호스트 경계 간에 통신 채널을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-194">The following illustration shows how interop marshaling and COM marshaling provide communications channels across process and host boundaries.</span></span>  
  
 <span data-ttu-id="2b0a1-195">![COM 마샬링](../../../docs/framework/interop/media/interophost.gif "interophost")</span><span class="sxs-lookup"><span data-stu-id="2b0a1-195">![COM marshaling](../../../docs/framework/interop/media/interophost.gif "interophost")</span></span>  
<span data-ttu-id="2b0a1-196">크로스 프로세스 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-196">Cross-process marshaling</span></span>  
  
### <a name="preserving-identity"></a><span data-ttu-id="2b0a1-197">ID 유지</span><span class="sxs-lookup"><span data-stu-id="2b0a1-197">Preserving Identity</span></span>  
 <span data-ttu-id="2b0a1-198">공용 언어 런타임은 관리되는 참조와 관리되지 않는 참조의 ID를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-198">The common language runtime preserves the identity of managed and unmanaged references.</span></span> <span data-ttu-id="2b0a1-199">다음 그림에서는 프로세스 및 호스트 경계 간에 관리되지 않는 직접 참조(위쪽 행)와 관리되는 직접 참조(아래쪽 행)의 흐름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-199">The following illustration shows the flow of direct unmanaged references (top row) and direct managed references (bottom row) across process and host boundaries.</span></span>  
  
 <span data-ttu-id="2b0a1-200">![COM 호출 가능 래퍼 및 런타임 호출 가능 래퍼](../../../docs/framework/interop/media/interopdirectref.gif "interopdirectref")</span><span class="sxs-lookup"><span data-stu-id="2b0a1-200">![COM callable wrapper and runtime callable wrapper](../../../docs/framework/interop/media/interopdirectref.gif "interopdirectref")</span></span>  
<span data-ttu-id="2b0a1-201">프로세스 및 호스트 경계 간에 전달되는 참조</span><span class="sxs-lookup"><span data-stu-id="2b0a1-201">Reference passing across process and host boundaries</span></span>  
  
 <span data-ttu-id="2b0a1-202">다음 그림에서</span><span class="sxs-lookup"><span data-stu-id="2b0a1-202">In this illustration:</span></span>  
  
-   <span data-ttu-id="2b0a1-203">관리되지 않는 클라이언트는 원격 호스트에서 이 참조를 가져오는 관리되는 개체로부터 COM 개체에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-203">An unmanaged client gets a reference to a COM object from a managed object that gets this reference from a remote host.</span></span> <span data-ttu-id="2b0a1-204">원격 메커니즘은 DCOM입니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-204">The remoting mechanism is DCOM.</span></span>  
  
-   <span data-ttu-id="2b0a1-205">관리되는 클라이언트는 원격 호스트에서 이 참조를 가져오는 COM 개체로부터 관리되는 개체에 대한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-205">A managed client gets a reference to a managed object from a COM object that gets this reference from a remote host.</span></span> <span data-ttu-id="2b0a1-206">원격 메커니즘은 DCOM입니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-206">The remoting mechanism is DCOM.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b0a1-207">관리되는 서버의 내보낸 형식 라이브러리를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-207">The exported type library of the managed server must be registered.</span></span>  
  
 <span data-ttu-id="2b0a1-208">호출자와 호출 수신자 간의 프로세스 경계 수는 관련이 없습니다. in-process 및 out-of-process 호출에 대해 동일한 직접 참조가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-208">The number of process boundaries between caller and callee is irrelevant; the same direct referencing occurs for in-process and out-of-process calls.</span></span>  
  
### <a name="managed-remoting"></a><span data-ttu-id="2b0a1-209">관리되는 원격</span><span class="sxs-lookup"><span data-stu-id="2b0a1-209">Managed Remoting</span></span>  
 <span data-ttu-id="2b0a1-210">런타임에서는 프로세스 및 호스트 경계를 넘은 관리되는 개체 간에 통신 채널을 설정하는 데 사용할 수 있는 관리되는 원격 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-210">The runtime also provides managed remoting, which you can use to establish a communications channel between managed objects across process and host boundaries.</span></span> <span data-ttu-id="2b0a1-211">관리되는 원격 기능은 다음 그림과 같이 통신 구성 요소 간의 방화벽을 수용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-211">Managed remoting can accommodate a firewall between the communicating components, as the following illustration shows.</span></span>  
  
 <span data-ttu-id="2b0a1-212">![SOAP 또는 TcpChannel](../../../docs/framework/interop/media/interopremotesoap.gif "interopremotesoap")</span><span class="sxs-lookup"><span data-stu-id="2b0a1-212">![SOAP or TcpChannel](../../../docs/framework/interop/media/interopremotesoap.gif "interopremotesoap")</span></span>  
<span data-ttu-id="2b0a1-213">SOAP 또는 TcpChannel 클래스를 사용하는 방화벽을 통한 원격 호출</span><span class="sxs-lookup"><span data-stu-id="2b0a1-213">Remote calls across firewalls using SOAP or the TcpChannel class</span></span>  
  
 <span data-ttu-id="2b0a1-214">[서비스 구성 요소](http://msdn.microsoft.com/en-us/f109ee24-81ad-4d99-9892-51ac6f34978c)와 COM 간의 호출과 같은 관리되지 않는 일부 호출은 SOAP를 채널로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-214">Some unmanaged calls can be channeled through SOAP, such as the calls between [serviced components](http://msdn.microsoft.com/en-us/f109ee24-81ad-4d99-9892-51ac6f34978c) and COM.</span></span>  
  
 [<span data-ttu-id="2b0a1-215">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="2b0a1-215">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="2b0a1-216">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2b0a1-216">Related Topics</span></span>  
  
|<span data-ttu-id="2b0a1-217">제목</span><span class="sxs-lookup"><span data-stu-id="2b0a1-217">Title</span></span>|<span data-ttu-id="2b0a1-218">설명</span><span class="sxs-lookup"><span data-stu-id="2b0a1-218">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2b0a1-219">기본 마샬링 동작</span><span class="sxs-lookup"><span data-stu-id="2b0a1-219">Default Marshaling Behavior</span></span>](../../../docs/framework/interop/default-marshaling-behavior.md)|<span data-ttu-id="2b0a1-220">Interop 마샬링 서비스에서 데이터를 마샬링하는 데 사용하는 규칙을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-220">Describes the rules that the interop marshaling service uses to marshal data.</span></span>|  
|[<span data-ttu-id="2b0a1-221">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-221">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)|<span data-ttu-id="2b0a1-222">메서드 매개 변수를 선언하고 관리되지 않는 라이브러리에서 내보낸 함수에 인수를 전달하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-222">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>|  
|[<span data-ttu-id="2b0a1-223">COM Interop를 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="2b0a1-223">Marshaling Data with COM Interop</span></span>](../../../docs/framework/interop/marshaling-data-with-com-interop.md)|<span data-ttu-id="2b0a1-224">COM 래퍼를 사용자 지정하여 마샬링 동작을 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-224">Describes how to customize COM wrappers to alter marshaling behavior.</span></span>|  
|[<span data-ttu-id="2b0a1-225">방법: 관리 코드 DCOM을 WCF로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2b0a1-225">How to: Migrate Managed-Code DCOM to WCF</span></span>](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)|<span data-ttu-id="2b0a1-226">DCOM에서 WCF로 마이그레이션하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-226">Describes how to migrate from DCOM to WCF.</span></span>|  
|[<span data-ttu-id="2b0a1-227">방법: HRESULT 및 예외 매핑</span><span class="sxs-lookup"><span data-stu-id="2b0a1-227">How to: Map HRESULTs and Exceptions</span></span>](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md)|<span data-ttu-id="2b0a1-228">사용자 지정 예외를 HRESULT에 매핑하는 방법을 설명하고 각 HRESULT와 .NET Framework에 있는 해당 예외 클래스 간의 전체 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-228">Describes how to map custom exceptions to HRESULTs and provides the complete mapping from each HRESULT to its comparable exception class in the .NET Framework.</span></span>|  
|[<span data-ttu-id="2b0a1-229">제네릭 형식을 통한 상호 운용</span><span class="sxs-lookup"><span data-stu-id="2b0a1-229">Interoperating Using Generic Types</span></span>](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)|<span data-ttu-id="2b0a1-230">COM 상호 운용성을 위해 제네릭 형식을 사용할 때 지원되는 작업을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-230">Describes which actions are supported when using generic types for COM interoperability.</span></span>|  
|[<span data-ttu-id="2b0a1-231">비관리 코드와의 상호 운용</span><span class="sxs-lookup"><span data-stu-id="2b0a1-231">Interoperating with Unmanaged Code</span></span>](../../../docs/framework/interop/index.md)|<span data-ttu-id="2b0a1-232">공용 언어 런타임에서 제공하는 상호 운용성 서비스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-232">Describes interoperability services provided by the common language runtime.</span></span>|  
|[<span data-ttu-id="2b0a1-233">고급 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="2b0a1-233">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)|<span data-ttu-id="2b0a1-234">COM 구성 요소를 .NET Framework 응용 프로그램으로 통합하는 방법에 대한 추가정보 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-234">Provides links to more information about incorporating COM components into your .NET Framework application.</span></span>|  
|[<span data-ttu-id="2b0a1-235">상호 운용을 위한 디자인 고려 사항</span><span class="sxs-lookup"><span data-stu-id="2b0a1-235">Design Considerations for Interoperation</span></span>](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)|<span data-ttu-id="2b0a1-236">통합된 COM 구성 요소를 작성하기 위한 팁을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b0a1-236">Provides tips for writing integrated COM components.</span></span>|  
  
 [<span data-ttu-id="2b0a1-237">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="2b0a1-237">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="2b0a1-238">참조</span><span class="sxs-lookup"><span data-stu-id="2b0a1-238">Reference</span></span>  
 <xref:System.Runtime.InteropServices?displayProperty=nameWithType>  
  
 [<span data-ttu-id="2b0a1-239">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="2b0a1-239">Back to top</span></span>](#top)
