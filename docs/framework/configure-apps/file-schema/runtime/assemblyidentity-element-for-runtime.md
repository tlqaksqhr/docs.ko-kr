---
title: "&lt;assemblyIdentity&gt; 요소에 대 한 &lt;런타임&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
caps.latest.revision: "17"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 0dadf0e07f5e3a9f9152ae7cd57c62721402bff0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltassemblyidentitygt-element-for-ltruntimegt"></a><span data-ttu-id="05bd5-102">&lt;assemblyIdentity&gt; 요소에 대 한 &lt;런타임&gt;</span><span class="sxs-lookup"><span data-stu-id="05bd5-102">&lt;assemblyIdentity&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="05bd5-103">어셈블리에 대 한 식별 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="05bd5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="05bd5-104">\<configuration></span></span>  
<span data-ttu-id="05bd5-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="05bd5-105">\<runtime></span></span>  
<span data-ttu-id="05bd5-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="05bd5-106">\<assemblyBinding></span></span>  
<span data-ttu-id="05bd5-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="05bd5-107">\<dependentAssembly></span></span>  
<span data-ttu-id="05bd5-108">\<assemblyIdentity ></span><span class="sxs-lookup"><span data-stu-id="05bd5-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05bd5-109">구문</span><span class="sxs-lookup"><span data-stu-id="05bd5-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05bd5-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="05bd5-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05bd5-112">특성</span><span class="sxs-lookup"><span data-stu-id="05bd5-112">Attributes</span></span>  
  
|<span data-ttu-id="05bd5-113">특성</span><span class="sxs-lookup"><span data-stu-id="05bd5-113">Attribute</span></span>|<span data-ttu-id="05bd5-114">설명</span><span class="sxs-lookup"><span data-stu-id="05bd5-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="05bd5-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="05bd5-116">어셈블리의 이름</span><span class="sxs-lookup"><span data-stu-id="05bd5-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="05bd5-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="05bd5-118">언어 및 국가/지역 어셈블리를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="05bd5-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="05bd5-120">어셈블리의 강력한 이름을 지정 하는 16 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="05bd5-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="05bd5-122">중 하나 값 "x86", "amd64", "msil" 또는 "ia64" 특정 프로세서 관련 코드가 포함 된 어셈블리에 대 한 프로세서 아키텍처를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="05bd5-123">값은 대/소문자 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-123">The values are not case-sensitive.</span></span> <span data-ttu-id="05bd5-124">특성은 다른 값을 전체 할당 `<assemblyIdentity>` 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="05bd5-125"><xref:System.Reflection.ProcessorArchitecture>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05bd5-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="05bd5-126">processorArchitecture 특성</span><span class="sxs-lookup"><span data-stu-id="05bd5-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="05bd5-127">값</span><span class="sxs-lookup"><span data-stu-id="05bd5-127">Value</span></span>|<span data-ttu-id="05bd5-128">설명</span><span class="sxs-lookup"><span data-stu-id="05bd5-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="05bd5-129">64 비트 AMD 프로세서 에서만입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-129">A 64-bit AMD processor only.</span></span>|  
|`ia64`|<span data-ttu-id="05bd5-130">64 비트 Intel 프로세서만 합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-130">A 64-bit Intel processor only.</span></span>|  
|`msil`|<span data-ttu-id="05bd5-131">중립 단어 당 비트 및 프로세서에 대해</span><span class="sxs-lookup"><span data-stu-id="05bd5-131">Neutral with respect to processor and bits-per-word</span></span>|  
|`x86`|<span data-ttu-id="05bd5-132">32 비트 Intel 프로세서, 네이티브 또는 Windows on Windows (WOW) 환경의 64 비트 플랫폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-132">A 32-bit Intel processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05bd5-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-133">Child Elements</span></span>  
 <span data-ttu-id="05bd5-134">없음</span><span class="sxs-lookup"><span data-stu-id="05bd5-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05bd5-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-135">Parent Elements</span></span>  
  
|<span data-ttu-id="05bd5-136">요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-136">Element</span></span>|<span data-ttu-id="05bd5-137">설명</span><span class="sxs-lookup"><span data-stu-id="05bd5-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="05bd5-138">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="05bd5-139">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="05bd5-140">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="05bd5-141">하나를 사용 하 여 `<dependentAssembly>` 각 어셈블리에 대 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="05bd5-142">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05bd5-143">설명</span><span class="sxs-lookup"><span data-stu-id="05bd5-143">Remarks</span></span>  
 <span data-ttu-id="05bd5-144">모든  **\<dependentAssembly >** 요소 하나가 있어야  **\<assemblyIdentity >** 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="05bd5-145">경우는 `processorArchitecture` 특성이 있으면는 `<assemblyIdentity>` 요소 해당 프로세서 아키텍처를 사용 하 여 어셈블리에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="05bd5-146">경우는 `processorArchitecture` 특성이 없으면는 `<assemblyIdentity>` 요소 모든 프로세서 아키텍처를 사용 하 여 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="05bd5-147">다음 예제에서는 두 개의 서로 다른 두 개의 프로세서 아키텍처를 대상으로 하 고 버전이 유지 하지 동기화 같은 이름의 두 어셈블리에 대 한 구성 파일을 보여 줍니다. X86 응용 프로그램을 실행 하는 경우 첫 번째 플랫폼 `<assemblyIdentity>` 요소 적용 하 고 다른는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="05bd5-148">X86 또는 ia64 이외의 플랫폼에서 응용 프로그램을 실행 하는 경우 모두 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"   
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"   
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"   
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="05bd5-149">구성 파일에 포함 하는 경우는 `<assemblyIdentity>` 없는 요소에 `processorArchitecture` 특성과 없이 요소 플랫폼과 일치 하는 요소가 포함 되지 않습니다는 `processorArchitecture` 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05bd5-150">예</span><span class="sxs-lookup"><span data-stu-id="05bd5-150">Example</span></span>  
 <span data-ttu-id="05bd5-151">다음 예제에서는 어셈블리에 대 한 정보를 제공 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-151">The following example shows how to provide information about an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="05bd5-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05bd5-152">See Also</span></span>  
 [<span data-ttu-id="05bd5-153">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="05bd5-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="05bd5-154">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="05bd5-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="05bd5-155">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="05bd5-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
