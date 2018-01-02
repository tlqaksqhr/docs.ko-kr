---
title: "&lt;legacyImpersonationPolicy&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#legacyImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/legacyImpersonationPolicy
helpviewer_keywords:
- <legacyImpersonationPolicy> element
- legacyImpersonationPolicy element
ms.assetid: 6e00af10-42f3-4235-8415-1bb2db78394e
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: caeede11d8128af00beb5b1b3426e8c4a5406520
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltlegacyimpersonationpolicygt-element"></a><span data-ttu-id="856d9-102">&lt;legacyImpersonationPolicy&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="856d9-102">&lt;legacyImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="856d9-103">현재 스레드의 실행 컨텍스트 흐름 설정과 관계없이 Windows ID가 비동기 지점 간을 흐르지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-103">Specifies that the Windows identity does not flow across asynchronous points, regardless of the flow settings for the execution context on the current thread.</span></span>  
  
 <span data-ttu-id="856d9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="856d9-104">\<configuration></span></span>  
<span data-ttu-id="856d9-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="856d9-105">\<runtime></span></span>  
<span data-ttu-id="856d9-106">\<legacyImpersonationPolicy ></span><span class="sxs-lookup"><span data-stu-id="856d9-106">\<legacyImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="856d9-107">구문</span><span class="sxs-lookup"><span data-stu-id="856d9-107">Syntax</span></span>  
  
```xml  
<legacyImpersonationPolicy    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="856d9-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="856d9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="856d9-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="856d9-110">특성</span><span class="sxs-lookup"><span data-stu-id="856d9-110">Attributes</span></span>  
  
|<span data-ttu-id="856d9-111">특성</span><span class="sxs-lookup"><span data-stu-id="856d9-111">Attribute</span></span>|<span data-ttu-id="856d9-112">설명</span><span class="sxs-lookup"><span data-stu-id="856d9-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="856d9-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="856d9-114">지정 하는 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 관계 없이 전달 되지 않습니다는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-114">Specifies that the <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="856d9-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="856d9-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="856d9-116">값</span><span class="sxs-lookup"><span data-stu-id="856d9-116">Value</span></span>|<span data-ttu-id="856d9-117">설명</span><span class="sxs-lookup"><span data-stu-id="856d9-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="856d9-118"><xref:System.Security.Principal.WindowsIdentity>흐름에 따라 비동기 지점 간에 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-118"><xref:System.Security.Principal.WindowsIdentity> flows across asynchronous points depending upon the <xref:System.Threading.ExecutionContext> flow settings for the current thread.</span></span> <span data-ttu-id="856d9-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="856d9-120"><xref:System.Security.Principal.WindowsIdentity>비동기 지점 간에 관계 없이 전달 되지 않습니다는 <xref:System.Threading.ExecutionContext> 흐름 현재 스레드에 대 한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-120"><xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points, regardless of the <xref:System.Threading.ExecutionContext> flow settings on the current thread.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="856d9-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="856d9-121">Child Elements</span></span>  
 <span data-ttu-id="856d9-122">없음</span><span class="sxs-lookup"><span data-stu-id="856d9-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="856d9-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="856d9-123">Parent Elements</span></span>  
  
|<span data-ttu-id="856d9-124">요소</span><span class="sxs-lookup"><span data-stu-id="856d9-124">Element</span></span>|<span data-ttu-id="856d9-125">설명</span><span class="sxs-lookup"><span data-stu-id="856d9-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="856d9-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="856d9-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="856d9-128">설명</span><span class="sxs-lookup"><span data-stu-id="856d9-128">Remarks</span></span>  
 <span data-ttu-id="856d9-129">.NET Framework 버전 1.0 및 1.1에서는 <xref:System.Security.Principal.WindowsIdentity> 어떠한 사용자 지정 비동기 요소 간에 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-129">In the .NET Framework versions 1.0 and 1.1, the <xref:System.Security.Principal.WindowsIdentity> does not flow across any user-defined asynchronous points.</span></span> <span data-ttu-id="856d9-130">.NET Framework 버전 2.0 부터는 <xref:System.Threading.ExecutionContext> 응용 프로그램 도메인 내에서 비동기 지점 간에 전달 하며 현재 실행 중인 스레드에 대 한 정보를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-130">Starting with the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and it flows across asynchronous points within an application domain.</span></span> <span data-ttu-id="856d9-131"><xref:System.Security.Principal.WindowsIdentity> 이 실행 컨텍스트에 포함 되 고 따라서 흐르는 비동기 지점 간에 가장 컨텍스트의 있으면 것 흐릅니다도 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-131">The <xref:System.Security.Principal.WindowsIdentity> is included in this execution context and therefore also flows across the asynchronous points, which means that if an impersonation context exists, it will flow as well.</span></span>  
  
 <span data-ttu-id="856d9-132">.NET Framework 2.0 이상에서는 사용할 수 있습니다는 `<legacyImpersonationPolicy>` 를 지정 하는 요소 <xref:System.Security.Principal.WindowsIdentity> 비동기 지점 간에 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-132">Starting with the .NET Framework 2.0, you can use the `<legacyImpersonationPolicy>` element to specify that  <xref:System.Security.Principal.WindowsIdentity> does not flow across asynchronous points.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="856d9-133">공용 언어 런타임 (CLR)은 비관리 코드에 또는 Win32 함수를 직접 호출을 통해 관리 코드만와 같은 플랫폼을 통해 관리 되는 코드 외부에서 수행 된 가장의를 사용 하 여 수행 되는 작업을 호출 하는 가장 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-133">The common language runtime (CLR) is aware of impersonation operations performed using only managed code, not of impersonation performed outside of managed code, such as through platform invoke to unmanaged code or through direct calls to Win32 functions.</span></span> <span data-ttu-id="856d9-134">관리 되는 <xref:System.Security.Principal.WindowsIdentity> 경우가 아니면 개체 비동기 지점 간에 전달 될 수 있습니다는 `alwaysFlowImpersonationPolicy` 요소가 설정에 true로 (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span><span class="sxs-lookup"><span data-stu-id="856d9-134">Only managed <xref:System.Security.Principal.WindowsIdentity> objects can flow across asynchronous points, unless the `alwaysFlowImpersonationPolicy` element has been set to true (`<alwaysFlowImpersonationPolicy enabled="true"/>`).</span></span> <span data-ttu-id="856d9-135">설정의 `alwaysFlowImpersonationPolicy` 요소를 true로 Windows id 항상 가장이 수행 하는 방법에 관계 없이 비동기 요소 간에 전달 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-135">Setting the `alwaysFlowImpersonationPolicy` element to true specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span> <span data-ttu-id="856d9-136">자세한 내용을 비동기 지점 간에 관리 되지 않는 가장 흐르는 대 한 정보를 참조 하십시오. [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-136">For more information on flowing unmanaged impersonation across asynchronous points, see [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
 <span data-ttu-id="856d9-137">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-137">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="856d9-138">스레드 단위 별로 관리 되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-138">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="856d9-139">수정 하 여 스레드 단위 별로 흐름을 표시 하지 않을 수 있습니다는 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 사용 하 여는 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="856d9-139">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType> or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="856d9-140">공용 언어 런타임 (CLR)를 로드 하는 관리 되지 않는 호스팅 인터페이스 호출에입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-140">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="856d9-141">CLR을 로드 하는 관리 되지 않는 호스팅 인터페이스 (간단한 관리 되는 실행 파일) 대신 사용 하는 경우에 대 한 호출에서 특수 플래그를 지정할 수 있습니다는 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-141">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="856d9-142">전체 프로세스에 대 한 호환성 모드를 사용 하도록 설정 된 `flags` 에 대 한 매개 변수 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) STARTUP_LEGACY_IMPERSONATION를 합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-142">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to STARTUP_LEGACY_IMPERSONATION.</span></span>  
  
 <span data-ttu-id="856d9-143">자세한 내용은 참조는 [ \<alwaysFlowImpersonationPolicy > 요소](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-143">For more information, see the [\<alwaysFlowImpersonationPolicy> Element](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md).</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="856d9-144">구성 파일</span><span class="sxs-lookup"><span data-stu-id="856d9-144">Configuration File</span></span>  
 <span data-ttu-id="856d9-145">.NET Framework 응용 프로그램에서는이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-145">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="856d9-146">ASP.NET 응용 프로그램에 대 한 가장 흐름에서에서 구성할 수 있습니다 aspnet.config 파일에서 찾을 수는 \<Windows 폴더 > \Microsoft.NET\Framework\vx.x.xxxx 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-146">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="856d9-147">기본적으로 ASP.NET 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-147">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```  
configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="856d9-148">Asp.net에서는 대신, 가장의 흐름을 허용 하려면 다음 구성 설정을 사용 해야 합니다 명시적으로.</span><span class="sxs-lookup"><span data-stu-id="856d9-148">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="856d9-149">예</span><span class="sxs-lookup"><span data-stu-id="856d9-149">Example</span></span>  
 <span data-ttu-id="856d9-150">다음 예제에서는 비동기 지점에 걸쳐 Windows id를 전달 하지 않는 레거시 동작을 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="856d9-150">The following example shows how to specify the legacy behavior that does not flow the Windows identity across asynchronous points.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="856d9-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="856d9-151">See Also</span></span>  
 [<span data-ttu-id="856d9-152">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="856d9-152">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="856d9-153">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="856d9-153">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="856d9-154">\<alwaysFlowImpersonationPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="856d9-154">\<alwaysFlowImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/alwaysflowimpersonationpolicy-element.md)
