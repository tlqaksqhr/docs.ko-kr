---
title: '&lt;코드 베이스&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3b614546e8ed23cc1a5e169a33fb5878695037ae
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltcodebasegt-element"></a><span data-ttu-id="841a2-102">&lt;코드 베이스&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="841a2-102">&lt;codeBase&gt; Element</span></span>
<span data-ttu-id="841a2-103">공용 언어 런타임에서 어셈블리를 찾을 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-103">Specifies where the common language runtime can find an assembly.</span></span>  
  
 <span data-ttu-id="841a2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="841a2-104">\<configuration></span></span>  
<span data-ttu-id="841a2-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="841a2-105">\<runtime></span></span>  
<span data-ttu-id="841a2-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="841a2-106">\<assemblyBinding></span></span>  
<span data-ttu-id="841a2-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="841a2-107">\<dependentAssembly></span></span>  
<span data-ttu-id="841a2-108">\<s e ></span><span class="sxs-lookup"><span data-stu-id="841a2-108">\<codeBase></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="841a2-109">구문</span><span class="sxs-lookup"><span data-stu-id="841a2-109">Syntax</span></span>  
  
```xml  
   <codeBase    
version="Assembly version"  
href="URL of assembly"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="841a2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="841a2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="841a2-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="841a2-112">특성</span><span class="sxs-lookup"><span data-stu-id="841a2-112">Attributes</span></span>  
  
|<span data-ttu-id="841a2-113">특성</span><span class="sxs-lookup"><span data-stu-id="841a2-113">Attribute</span></span>|<span data-ttu-id="841a2-114">설명</span><span class="sxs-lookup"><span data-stu-id="841a2-114">Description</span></span>|  
|---------------|-----------------|  
|`href`|<span data-ttu-id="841a2-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="841a2-116">런타임에서 지정 된 버전의 어셈블리를 찾을 수 있는 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-116">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|  
|`version`|<span data-ttu-id="841a2-117">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="841a2-118">코드 베이스에 적용 됩니다. 어셈블리의 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-118">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="841a2-119">어셈블리 버전 번호의 형식은 *major.minor.build.revision*합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-119">The format of an assembly version number is *major.minor.build.revision*.</span></span>|  
  
## <a name="version-attribute"></a><span data-ttu-id="841a2-120">버전 특성</span><span class="sxs-lookup"><span data-stu-id="841a2-120">version Attribute</span></span>  
  
|<span data-ttu-id="841a2-121">값</span><span class="sxs-lookup"><span data-stu-id="841a2-121">Value</span></span>|<span data-ttu-id="841a2-122">설명</span><span class="sxs-lookup"><span data-stu-id="841a2-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="841a2-123">버전 번호의 각 부분에 대 한 유효한 값은 0부터 65535 까지입니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-123">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="841a2-124">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="841a2-124">Not applicable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="841a2-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="841a2-125">Child Elements</span></span>  
 <span data-ttu-id="841a2-126">없음</span><span class="sxs-lookup"><span data-stu-id="841a2-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="841a2-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="841a2-127">Parent Elements</span></span>  
  
|<span data-ttu-id="841a2-128">요소</span><span class="sxs-lookup"><span data-stu-id="841a2-128">Element</span></span>|<span data-ttu-id="841a2-129">설명</span><span class="sxs-lookup"><span data-stu-id="841a2-129">Description</span></span>|  
|-------------|-----------------|  
|`buildproviders`|<span data-ttu-id="841a2-130">사용자 지정 리소스 파일의 컴파일에 사용되는 빌드 공급자의 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-130">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="841a2-131">빌드 공급자 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-131">You can have any number of build providers.</span></span>|  
|`compilation`|<span data-ttu-id="841a2-132">ASP.NET에서 사용 하는 모든 컴파일 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-132">Configures all the compilation settings that ASP.NET uses.</span></span>|  
|`configuration`|<span data-ttu-id="841a2-133">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.web`|<span data-ttu-id="841a2-134">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-134">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="841a2-135">설명</span><span class="sxs-lookup"><span data-stu-id="841a2-135">Remarks</span></span>  
 <span data-ttu-id="841a2-136">런타임에서 사용에 대 한는  **\<s e >** 컴퓨터 구성 파일 또는 게시자 정책 파일에 설정, 파일을 리디렉션해야 어셈블리 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-136">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="841a2-137">응용 프로그램 구성 파일 없이 어셈블리 버전 리디렉션 codebase 설정을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-137">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="841a2-138">사용 하는 어셈블리 버전을 확인 한 후 런타임 버전을 결정 하는 파일의 코드 베이스 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-138">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="841a2-139">지정 된 없는 codebase가 런타임에서 어셈블리에 대 한 일반적으로 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-139">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>  
  
 <span data-ttu-id="841a2-140">어셈블리에 강력한 이름이 있으면 codebase 설정을 로컬 인트라넷 또는 인터넷에서 아무 곳 이나 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-140">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="841a2-141">전용 어셈블리를 어셈블리가 있는 경우 코드 베이스 설정은는 응용 프로그램의 디렉터리의 상대 경로 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-141">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>  
  
 <span data-ttu-id="841a2-142">강력한 이름 없이 어셈블리의 경우 버전이 무시 되 고 로더 사용에서 처음 나오는 \<s e > 내 \<dependentAssembly > 합니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-142">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="841a2-143">다른 어셈블리에 바인딩 리디렉션하는 응용 프로그램 구성 파일에 항목이 있으면 리디렉션 어셈블리 버전 바인딩 요청과 일치 하지 않는 경우에 우선을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-143">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesnt match the binding request.</span></span>  
  
## <a name="example"></a><span data-ttu-id="841a2-144">예제</span><span class="sxs-lookup"><span data-stu-id="841a2-144">Example</span></span>  
 <span data-ttu-id="841a2-145">다음 예제에서는 런타임에 어셈블리를 찾을 수를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="841a2-145">The following example shows how to specify where the runtime can find an assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="841a2-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="841a2-146">See Also</span></span>  
 [<span data-ttu-id="841a2-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="841a2-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="841a2-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="841a2-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="841a2-149">어셈블리 위치 지정</span><span class="sxs-lookup"><span data-stu-id="841a2-149">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)  
 [<span data-ttu-id="841a2-150">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="841a2-150">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
