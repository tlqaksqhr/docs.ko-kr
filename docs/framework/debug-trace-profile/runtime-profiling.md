---
title: "런타임 프로파일링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters
- common language runtime, profiling
- Perfmon.exe
- System Monitor
- profiling
- runtime, profiling
- profiling applications
- Performance Console
ms.assetid: ccd68284-f3a8-47b8-bc3f-92e5fe3a1640
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 876635cfe0349c734a61dcc827a6f9594bb2a5d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="runtime-profiling"></a><span data-ttu-id="9e90d-102">런타임 프로파일링</span><span class="sxs-lookup"><span data-stu-id="9e90d-102">Runtime Profiling</span></span>
<span data-ttu-id="9e90d-103">프로파일링은 모든 개발 또는 배포 시나리오에서 성능 데이터를 수집하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-103">Profiling is a method of gathering performance data in any development or deployment scenario.</span></span> <span data-ttu-id="9e90d-104">이 섹션은 응용 프로그램 성능에 대한 정보를 수집하려는 개발자 및 시스템 관리자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-104">This section is for developers and system administrators who want to gather information about application performance.</span></span>  
  
## <a name="tracking-performance-using-the-performance-monitor-perfmonexe"></a><span data-ttu-id="9e90d-105">성능 모니터(Perfmon.exe)를 사용하여 성능 추적</span><span class="sxs-lookup"><span data-stu-id="9e90d-105">Tracking Performance Using the Performance Monitor (Perfmon.exe)</span></span>  
 <span data-ttu-id="9e90d-106">성능 모니터는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 응용 프로그램 프로파일링에 사용하는 가장 쉬운 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-106">The Performance Monitor is the easiest tool to use to profile your [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] application.</span></span> <span data-ttu-id="9e90d-107">성능 모니터는 공용 언어 런타임과 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]이 함께 설치된 .NET Framework 성능 카운터의 데이터를 그래픽으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-107">The Performance Monitor graphically represents data found in the .NET Framework performance counters that are installed with the common language runtime and the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span> <span data-ttu-id="9e90d-108">이러한 카운터를 사용하여 메모리 관리에서 JIT(just-in-time) 컴파일러 성능에 이르기까지 모든 것을 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-108">These counters can be used to monitor everything from memory management to just-in-time (JIT) compiler performance.</span></span> <span data-ttu-id="9e90d-109">이렇게 하여 응용 프로그램이 사용하는 리소스에 대해 알 수 있으며 이는 응용 프로그램의 성능에 대한 간접적인 측정입니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-109">They tell you about the resources your application uses, which is an indirect measure of your application's performance.</span></span> <span data-ttu-id="9e90d-110">이러한 카운터를 사용하여 응용 프로그램이 내부적으로 작동하는 방식을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-110">Use these counters to understand how your application works internally.</span></span>  
  
#### <a name="to-run-perfmonexe-on-windows-vista-and-later-versions"></a><span data-ttu-id="9e90d-111">Windows Vista 이상 버전에서 Perfmon.exe를 실행하려면</span><span class="sxs-lookup"><span data-stu-id="9e90d-111">To run Perfmon.exe on Windows Vista and later versions</span></span>  
  
1.  <span data-ttu-id="9e90d-112">명령 프롬프트에서 **perfmon**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-112">At the command prompt, type **perfmon**.</span></span> <span data-ttu-id="9e90d-113">**성능 모니터** 콘솔이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-113">The **Performance Monitor** console appears.</span></span>  
  
2.  <span data-ttu-id="9e90d-114">**모니터링 도구** 폴더에서 **성능 모니터**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-114">In the **Monitoring Tools** folder, click **Performance Monitor**.</span></span>  
  
3.  <span data-ttu-id="9e90d-115">성능 모니터 도구 모음에서 **추가** 아이콘(더하기 기호)이 있는 경우 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-115">In the Performance Monitor toolbar, click the **Add** icon (the plus sign), if it is present.</span></span> <span data-ttu-id="9e90d-116">아이콘이 없는 경우 모니터 창을 마우스 오른쪽 단추로 클릭하고 **카운터 추가** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-116">If it is not present, right-click in the monitor window and select the **Add Counters** option.</span></span>  
  
     <span data-ttu-id="9e90d-117">그러면 **카운터 추가** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-117">This opens the **Add Counters** dialog box.</span></span> <span data-ttu-id="9e90d-118">**사용 가능한 카운터** 목록 상자에 사용 가능한 성능 개체가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-118">The **Available counters** list box displays the available performance objects.</span></span> <span data-ttu-id="9e90d-119">메모리 관리(**.NET CLR 메모리**), 상호 운용성(**.NET CLR Interop**), 예외 처리(**.NET CLR 예외**) 및 다중 스레딩(**.NET CLR LocksAndThreads**)에 대한 개체를 비롯한 .NET Framework 응용 프로그램에 대해 다수의 미리 정의된 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-119">There are a number of predefined objects for .NET Framework applications, including those for memory management (**.NET CLR Memory**), interoperability (**.NET CLR Interop**), exception handling (**.NET CLR Exceptions**), and multithreading (**.NET CLR LocksAndThreads**).</span></span> <span data-ttu-id="9e90d-120">각 성능 개체에는 많은 개별 성능 카운터가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-120">Each performance object includes a number of individual performance counters.</span></span> <span data-ttu-id="9e90d-121">성능 모니터에서 사용할 수 있는 성능 카운터 목록은 [Performance Counters](../../../docs/framework/debug-trace-profile/performance-counters.md)이 함께 설치된 .NET Framework 성능 카운터의 데이터를 그래픽으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-121">For a list of the performance counters available in Performance Monitor, see [Performance Counters](../../../docs/framework/debug-trace-profile/performance-counters.md).</span></span>  
  
4.  <span data-ttu-id="9e90d-122">지원되는 개별 성능 카운터의 목록을 보려면 성능 개체의 이름 옆에 있는 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-122">Select the check box next to a performance object's name to view the list of individual performance counters that it supports.</span></span>  
  
5.  <span data-ttu-id="9e90d-123">보려는 성능 카운터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-123">Click the performance counter you want to view.</span></span>  
  
6.  <span data-ttu-id="9e90d-124">**선택한 개체의 인스턴스** 목록 상자에서 **\<All instances>**를 클릭하여 공용 언어 런타임에 대한 성능 카운터를 전역적으로(시스템 전체에서) 모니터링하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-124">In the **Instances of selected object** list box, click **\<All instances>** to specify that you want to monitor the performance counter for the common language runtime globally (that is, on a system-wide basis).</span></span>  
  
     <span data-ttu-id="9e90d-125">또는</span><span class="sxs-lookup"><span data-stu-id="9e90d-125">-or-</span></span>  
  
     <span data-ttu-id="9e90d-126">**선택한 개체의 인스턴스** 목록 상자에서 응용 프로그램 이름을 클릭하여 해당 응용 프로그램에 대한 성능 카운터를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-126">In the **Instances of selected object** list box, click an application name to monitor the performance counter for that application.</span></span>  
  
     <span data-ttu-id="9e90d-127">여러 버전의 런타임을 구분하거나 이름이 같은 여러 응용 프로그램의 차이를 분명히 보여 주려면 레지스트리 키도 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-127">To differentiate multiple versions of the runtime, or to disambiguate multiple applications with the same name, you must also modify a registry key.</span></span> <span data-ttu-id="9e90d-128">자세한 내용은 [Performance Counters and In-Process Side-By-Side Applications](../../../docs/framework/debug-trace-profile/performance-counters-and-in-process-side-by-side-applications.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e90d-128">For more information, see [Performance Counters and In-Process Side-By-Side Applications](../../../docs/framework/debug-trace-profile/performance-counters-and-in-process-side-by-side-applications.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e90d-129">성능 콘솔이 실행되는 동안 새로운 성능 카운터가 설치되면 새로운 카운터를 표시하기 위해 성능 콘솔을 중지하고 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-129">When new performance counters are installed while the Performance console is running, stop and restart the Performance console to make the new counters visible.</span></span>  
  
 <span data-ttu-id="9e90d-130">특정 영역이나 원격 공유에 있는 어셈블리를 프로파일링하려면 성능 카운터를 실행하는 컴퓨터에서 원격 어셈블리를 완전히 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-130">If you want to profile an assembly that exists in a zone or on a remote share, make sure that the remote assembly has full trust on the computer that runs the performance counters.</span></span> <span data-ttu-id="9e90d-131">어셈블리를 충분히 신뢰하지 않는 경우 성능 카운터가 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-131">If the assembly does not have sufficient trust, the performance counters will not work.</span></span> <span data-ttu-id="9e90d-132">여러 다른 영역에 신뢰를 부여하는 데 관한 내용은 [Caspol.exe(코드 액세스 보안 정책 도구)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e90d-132">For information about granting trust to different zones, see [Caspol.exe (Code Access Security Policy Tool)](../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e90d-133">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 가 설치된 시스템에서 성능 모니터는 **를 사용하여 개발된 응용 프로그램의 일부 범주(예:** .NET CLR 데이터 **및**.NET CLR 네트워킹 [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)])에서 성능 카운터에 대한 데이터를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-133">On systems on which the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] is installed, the Performance Monitor may not display data for performance counters in some categories, such as **.NET CLR Data** and **.NET CLR Networking**, for applications that were developed using the [!INCLUDE[net_v11_short](../../../includes/net-v11-short-md.md)].</span></span> <span data-ttu-id="9e90d-134">이 경우, [\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md) 요소를 응용 프로그램의 구성 파일에 추가하여 성능 모니터가 이 데이터를 표시하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-134">If this is the case, you can configure Performance Monitor to display this data by adding the [\<forcePerformanceCounterUniqueSharedMemoryReads>](../../../docs/framework/configure-apps/file-schema/runtime/forceperformancecounteruniquesharedmemoryreads-element.md) element to the application's configuration file.</span></span>  
  
## <a name="reading-and-creating-performance-counters-programmatically"></a><span data-ttu-id="9e90d-135">프로그래밍 방식으로 성능 카운터 읽기 및 만들기</span><span class="sxs-lookup"><span data-stu-id="9e90d-135">Reading and Creating Performance Counters Programmatically</span></span>  
 <span data-ttu-id="9e90d-136">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 은 성능 콘솔에서 사용할 수 있는 동일한 성능 정보를 프로그래밍 방식으로 액세스하기 위해 사용할 수 있는 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-136">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides classes you can use to programmatically access the same performance information that is available in the Performance console.</span></span> <span data-ttu-id="9e90d-137">또한 이러한 클래스를 사용하여 사용자 지정 성능 카운터를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-137">You can also use these classes to create custom performance counters.</span></span> <span data-ttu-id="9e90d-138">다음 표에서는 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서 제공하는 일부 성능 모니터링 클래스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-138">The following table describes some of the performance monitoring classes that are provided in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
|<span data-ttu-id="9e90d-139">클래스</span><span class="sxs-lookup"><span data-stu-id="9e90d-139">Class</span></span>|<span data-ttu-id="9e90d-140">설명</span><span class="sxs-lookup"><span data-stu-id="9e90d-140">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType>|<span data-ttu-id="9e90d-141">Windows NT 성능 카운터 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-141">Represents a Windows NT performance counter component.</span></span> <span data-ttu-id="9e90d-142">이 클래스를 사용하여 기존의 미리 정의된 카운터 또는 사용자 지정 카운터를 읽고 성능 데이터를 사용자 지정 카운터에 쓰거나 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-142">Use this class to read existing predefined or custom counters and publish (write) performance data to custom counters.</span></span>|  
|<xref:System.Diagnostics.PerformanceCounterCategory?displayProperty=nameWithType>|<span data-ttu-id="9e90d-143">컴퓨터에서 카운터 및 카운터 범주를 조작하기 위한 여러 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-143">Provides several methods for interacting with counters and categories of counters on the computer.</span></span>|  
|<xref:System.Diagnostics.PerformanceCounterInstaller?displayProperty=nameWithType>|<span data-ttu-id="9e90d-144">`PerformanceCounter` 구성 요소에 대해 설치 관리자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-144">Specifies an installer for the `PerformanceCounter` component.</span></span>|  
|<xref:System.Diagnostics.PerformanceCounterType?displayProperty=nameWithType>|<span data-ttu-id="9e90d-145">`NextValue` 에 대한 `PerformanceCounter`메서드를 계산하는 수식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e90d-145">Specifies the formula to calculate the `NextValue` method for a `PerformanceCounter`.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e90d-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e90d-146">See Also</span></span>  
 [<span data-ttu-id="9e90d-147">Performance Counters</span><span class="sxs-lookup"><span data-stu-id="9e90d-147">Performance Counters</span></span>](../../../docs/framework/debug-trace-profile/performance-counters.md)
