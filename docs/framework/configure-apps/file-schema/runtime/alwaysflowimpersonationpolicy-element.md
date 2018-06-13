---
title: '&lt;alwaysFlowImpersonationPolicy&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/alwaysFlowImpersonationPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#alwaysFlowImpersonationPolicy
helpviewer_keywords:
- alwaysFlowImpersonationPolicy element
- <alwaysFlowImpersonationPolicy> element
ms.assetid: ee622801-9e46-470b-85ab-88c4b1dd2ee1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5cc704bbf8631936dbbeb3539ea5ed0d8499f378
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752275"
---
# <a name="ltalwaysflowimpersonationpolicygt-element"></a><span data-ttu-id="36934-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span><span class="sxs-lookup"><span data-stu-id="36934-102">&lt;alwaysFlowImpersonationPolicy&gt; Element</span></span>
<span data-ttu-id="36934-103">가장을 수행하는 방법과 관계없이 Windows ID가 항상 비동기 지점 간을 흐르도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-103">Specifies that the Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>  
  
 <span data-ttu-id="36934-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="36934-104">\<configuration></span></span>  
<span data-ttu-id="36934-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="36934-105">\<runtime></span></span>  
<span data-ttu-id="36934-106">\<alwaysFlowImpersonationPolicy></span><span class="sxs-lookup"><span data-stu-id="36934-106">\<alwaysFlowImpersonationPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36934-107">구문</span><span class="sxs-lookup"><span data-stu-id="36934-107">Syntax</span></span>  
  
```xml  
<alwaysFlowImpersonationPolicy    
  enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36934-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36934-108">Attributes and Elements</span></span>  
 <span data-ttu-id="36934-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36934-110">특성</span><span class="sxs-lookup"><span data-stu-id="36934-110">Attributes</span></span>  
  
|<span data-ttu-id="36934-111">특성</span><span class="sxs-lookup"><span data-stu-id="36934-111">Attribute</span></span>|<span data-ttu-id="36934-112">설명</span><span class="sxs-lookup"><span data-stu-id="36934-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="36934-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="36934-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="36934-114">비동기 지점에 걸쳐 Windows id가 전달 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="36934-114">Indicates whether the Windows identity flows across asynchronous points.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="36934-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="36934-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="36934-116">값</span><span class="sxs-lookup"><span data-stu-id="36934-116">Value</span></span>|<span data-ttu-id="36934-117">설명</span><span class="sxs-lookup"><span data-stu-id="36934-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="36934-118">통해 가장이 수행 하지 않으면 identity 비동기 지점 간에 이동 하지 않는 Windows 관리 되는 메서드 같은 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-118">The Windows identity does not flow across asynchronous points, unless the impersonation is performed through managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A>.</span></span> <span data-ttu-id="36934-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="36934-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="36934-120">Windows id는 항상 가장이 수행 하는 방법에 관계 없이 비동기 요소 간에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-120">The Windows identity always flows across asynchronous points, regardless of how impersonation was performed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36934-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36934-121">Child Elements</span></span>  
 <span data-ttu-id="36934-122">없음</span><span class="sxs-lookup"><span data-stu-id="36934-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36934-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36934-123">Parent Elements</span></span>  
  
|<span data-ttu-id="36934-124">요소</span><span class="sxs-lookup"><span data-stu-id="36934-124">Element</span></span>|<span data-ttu-id="36934-125">설명</span><span class="sxs-lookup"><span data-stu-id="36934-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="36934-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="36934-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="36934-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36934-128">설명</span><span class="sxs-lookup"><span data-stu-id="36934-128">Remarks</span></span>  
 <span data-ttu-id="36934-129">.NET Framework 버전 1.0 및 1.1에서는 Windows id 비동기 지점 간에 전달 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36934-129">In the .NET Framework versions 1.0 and 1.1, the Windows identity does not flow across asynchronous points.</span></span> <span data-ttu-id="36934-130">.NET Framework 버전 2.0에는 <xref:System.Threading.ExecutionContext> 개체는 현재 실행 중인 스레드에 대 한 정보가 포함 된 응용 프로그램 도메인 내에서 비동기 지점 간에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-130">In the .NET Framework version 2.0, there is an <xref:System.Threading.ExecutionContext> object that contains information about the currently executing thread, and flows it across asynchronous points within an application domain.</span></span> <span data-ttu-id="36934-131"><xref:System.Security.Principal.WindowsIdentity> 또한를 사용 하 여 가장이 수행 하는 경우 비동기 지점에서 전송 되는 정보의 일부로 흐름 관리 되는 메서드 같은 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> 플랫폼 등의 다른 방법을 통해서가 아니라 네이티브 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-131">The <xref:System.Security.Principal.WindowsIdentity> also flows as part of the information that flows across the asynchronous points, provided the impersonation was achieved using managed methods such as <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> and not through other means such as platform invoke to native methods.</span></span> <span data-ttu-id="36934-132">이 요소는 Windows id가 가장이 수행 하는 방법에 관계 없이 비동기 요소 간에 전달 지정에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36934-132">This element is used to specify that the Windows identity does flow across asynchronous points, regardless of how the impersonation was achieved.</span></span>  
  
 <span data-ttu-id="36934-133">다른 두 가지 방법으로이 기본 동작을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36934-133">You can alter this default behavior in two other ways:</span></span>  
  
1.  <span data-ttu-id="36934-134">스레드 단위 별로 관리 되는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="36934-134">In managed code on a per-thread basis.</span></span>  
  
     <span data-ttu-id="36934-135">수정 하 여 스레드 단위 별로 흐름을 표시 하지 않을 수 있습니다는 <xref:System.Threading.ExecutionContext> 및 <xref:System.Security.SecurityContext> 설정을 사용 하 여는 <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, 또는 <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="36934-135">You can suppress the flow on a per-thread basis by modifying the <xref:System.Threading.ExecutionContext> and <xref:System.Security.SecurityContext> settings by using the <xref:System.Threading.ExecutionContext.SuppressFlow%2A?displayProperty=nameWithType>, <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A?displayProperty=nameWithType>, or <xref:System.Security.SecurityContext.SuppressFlow%2A?displayProperty=nameWithType> method.</span></span>  
  
2.  <span data-ttu-id="36934-136">공용 언어 런타임 (CLR)를 로드 하는 관리 되지 않는 호스팅 인터페이스 호출에입니다.</span><span class="sxs-lookup"><span data-stu-id="36934-136">In the call to the unmanaged hosting interface to load the common language runtime (CLR).</span></span>  
  
     <span data-ttu-id="36934-137">CLR을 로드 하는 관리 되지 않는 호스팅 인터페이스 (간단한 관리 되는 실행 파일) 대신 사용 하는 경우에 대 한 호출에서 특수 플래그를 지정할 수 있습니다는 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="36934-137">If an unmanaged hosting interface (instead of a simple managed executable) is used to load the CLR, you can specify a special flag in the call to the [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function.</span></span> <span data-ttu-id="36934-138">전체 프로세스에 대 한 호환성 모드를 사용 하도록 설정 된 `flags` 에 대 한 매개 변수 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 를 `STARTUP_ALWAYSFLOW_IMPERSONATION`합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-138">To enable the compatibility mode for the entire process, set the `flags` parameter for [CorBindToRuntimeEx Function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) to `STARTUP_ALWAYSFLOW_IMPERSONATION`.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="36934-139">구성 파일</span><span class="sxs-lookup"><span data-stu-id="36934-139">Configuration File</span></span>  
 <span data-ttu-id="36934-140">.NET Framework 응용 프로그램에서는이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36934-140">In a .NET Framework application, this element can be used only in the application configuration file.</span></span>  
  
 <span data-ttu-id="36934-141">ASP.NET 응용 프로그램에 대 한 가장 흐름에서에서 구성할 수 있습니다 aspnet.config 파일에서 찾을 수는 \<Windows 폴더 > \Microsoft.NET\Framework\vx.x.xxxx 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="36934-141">For an ASP.NET application, the impersonation flow can be configured in the aspnet.config file found in the \<Windows Folder>\Microsoft.NET\Framework\vx.x.xxxx directory.</span></span>  
  
 <span data-ttu-id="36934-142">기본적으로 ASP.NET 다음 구성 설정을 사용 하 여 aspnet.config 파일에서 가장 흐름을 비활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="36934-142">ASP.NET by default disables the impersonation flow in the aspnet.config file by using the following configuration settings:</span></span>  
  
```xml
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="true"/>  
      <alwaysFlowImpersonationPolicy enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="36934-143">Asp.net에서는 대신, 가장의 흐름을 허용 하려면 다음 구성 설정을 사용 해야 합니다 명시적으로.</span><span class="sxs-lookup"><span data-stu-id="36934-143">In ASP.NET, if you want to allow the flow of impersonation instead, you must explicitly use the following configuration settings:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <legacyImpersonationPolicy enabled="false"/>  
      <alwaysFlowImpersonationPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="36934-144">예제</span><span class="sxs-lookup"><span data-stu-id="36934-144">Example</span></span>  
 <span data-ttu-id="36934-145">다음 예제에서는 관리 되는 메서드 이외의 방법을 통해 가장이 수행 하는 경우에 비동기 지점에 걸쳐 Windows id가 전달 되도록 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36934-145">The following example shows how to specify that the Windows identity flows across asynchronous points, even when the impersonation is achieved through means other than managed methods.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <alwaysFlowImpersonationPolicy enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36934-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36934-146">See Also</span></span>  
 [<span data-ttu-id="36934-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="36934-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="36934-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="36934-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="36934-149">\<legacyImpersonationPolicy > 요소</span><span class="sxs-lookup"><span data-stu-id="36934-149">\<legacyImpersonationPolicy> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)
