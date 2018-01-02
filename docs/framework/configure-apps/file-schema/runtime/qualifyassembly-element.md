---
title: "&lt;qualifyAssembly&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7da2e1ac5c16f6e481c974794efceb12f102b1a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltqualifyassemblygt-element"></a><span data-ttu-id="10a21-102">&lt;qualifyAssembly&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="10a21-102">&lt;qualifyAssembly&gt; Element</span></span>
<span data-ttu-id="10a21-103">부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="10a21-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="10a21-104">\<configuration></span></span>  
<span data-ttu-id="10a21-105">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="10a21-105">\<runtime></span></span>  
<span data-ttu-id="10a21-106">\<assemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="10a21-106">\<assemblyBinding></span></span>  
<span data-ttu-id="10a21-107">\<qualifyAssembly ></span><span class="sxs-lookup"><span data-stu-id="10a21-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10a21-108">구문</span><span class="sxs-lookup"><span data-stu-id="10a21-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10a21-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="10a21-109">Attributes and Elements</span></span>  
 <span data-ttu-id="10a21-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10a21-111">특성</span><span class="sxs-lookup"><span data-stu-id="10a21-111">Attributes</span></span>  
  
|<span data-ttu-id="10a21-112">특성</span><span class="sxs-lookup"><span data-stu-id="10a21-112">Attribute</span></span>|<span data-ttu-id="10a21-113">설명</span><span class="sxs-lookup"><span data-stu-id="10a21-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="10a21-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="10a21-115">코드에 표시 된 대로 어셈블리의 부분 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="10a21-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="10a21-117">전역 어셈블리 캐시에 표시 되는 어셈블리의 전체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10a21-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="10a21-118">Child Elements</span></span>  
 <span data-ttu-id="10a21-119">없음</span><span class="sxs-lookup"><span data-stu-id="10a21-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10a21-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="10a21-120">Parent Elements</span></span>  
  
|<span data-ttu-id="10a21-121">요소</span><span class="sxs-lookup"><span data-stu-id="10a21-121">Element</span></span>|<span data-ttu-id="10a21-122">설명</span><span class="sxs-lookup"><span data-stu-id="10a21-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="10a21-123">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="10a21-124">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="10a21-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10a21-126">설명</span><span class="sxs-lookup"><span data-stu-id="10a21-126">Remarks</span></span>  
 <span data-ttu-id="10a21-127">호출 된 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 부분 어셈블리 이름을 사용 하 여 메서드를 공용 언어 런타임 응용 프로그램 기본 디렉터리에만 어셈블리에 대 한 조회를 사용 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="10a21-128">사용 하 여  **\<qualifyAssembly >** 전체 어셈블리 정보 (이름, 버전, 공개 키 토큰 및 문화권)를 제공 하 여 검색 하려면 공용 언어 런타임이 응용 프로그램 구성 파일의 요소 전역 어셈블리 캐시에서 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="10a21-129">**fullName** 특성의 어셈블리 id는 4 개의 필드를 포함 해야 합니다: 이름, 버전, 공개 키 토큰 및 culture입니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="10a21-130">**partialName** 특성 어셈블리를 부분적으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="10a21-131">어셈블리의 텍스트 이름 (가장 일반적인 경우), 이상 지정 해야 하지만 버전, 공개 키 토큰 또는 문화권 (또는 일부 4의 임의 조합)을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="10a21-132">**partialName** 프로그램 호출에 지정 된 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="10a21-133">예를 들어 지정할 수 없습니다 `"math"` 로 **partialName** 구성 파일 및 호출 특성 `Assembly.Load("math, Version=3.3.3.3")` 코드에서입니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a21-134">예</span><span class="sxs-lookup"><span data-stu-id="10a21-134">Example</span></span>  
 <span data-ttu-id="10a21-135">다음 예에서는 논리적으로 호출을 변환 `Assembly.Load("math")` 에 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`합니다.</span><span class="sxs-lookup"><span data-stu-id="10a21-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="10a21-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10a21-136">See Also</span></span>  
 [<span data-ttu-id="10a21-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="10a21-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="10a21-138">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="10a21-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="10a21-139">NIB: 부분 어셈블리 참조</span><span class="sxs-lookup"><span data-stu-id="10a21-139">NIB: Partial Assembly References</span></span>](http://msdn.microsoft.com/en-us/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
