---
title: '&lt;l i c y&gt; 요소'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2cc3b7220fe34f5dc049a3da71b160a88f82fdb1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746100"
---
# <a name="ltpublisherpolicygt-element"></a><span data-ttu-id="acce9-102">&lt;l i c y&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="acce9-102">&lt;publisherPolicy&gt; Element</span></span>
<span data-ttu-id="acce9-103">런타임이 게시자 정책을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-103">Specifies whether the runtime applies publisher policy.</span></span>  
  
 <span data-ttu-id="acce9-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="acce9-104">\<configuration></span></span>  
<span data-ttu-id="acce9-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="acce9-105">\<runtime></span></span>  
<span data-ttu-id="acce9-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="acce9-106">\<assemblyBinding></span></span>  
<span data-ttu-id="acce9-107">\<dependentAssembly ></span><span class="sxs-lookup"><span data-stu-id="acce9-107">\<dependentAssembly></span></span>  
<span data-ttu-id="acce9-108">\<l i c y ></span><span class="sxs-lookup"><span data-stu-id="acce9-108">\<publisherPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acce9-109">구문</span><span class="sxs-lookup"><span data-stu-id="acce9-109">Syntax</span></span>  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="acce9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="acce9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="acce9-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="acce9-112">특성</span><span class="sxs-lookup"><span data-stu-id="acce9-112">Attributes</span></span>  
  
|<span data-ttu-id="acce9-113">특성</span><span class="sxs-lookup"><span data-stu-id="acce9-113">Attribute</span></span>|<span data-ttu-id="acce9-114">설명</span><span class="sxs-lookup"><span data-stu-id="acce9-114">Description</span></span>|  
|---------------|-----------------|  
|`apply`|<span data-ttu-id="acce9-115">게시자 정책을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-115">Specifies whether to apply publisher policy.</span></span>|  
  
## <a name="apply-attribute"></a><span data-ttu-id="acce9-116">특성 적용</span><span class="sxs-lookup"><span data-stu-id="acce9-116">apply Attribute</span></span>  
  
|<span data-ttu-id="acce9-117">값</span><span class="sxs-lookup"><span data-stu-id="acce9-117">Value</span></span>|<span data-ttu-id="acce9-118">설명</span><span class="sxs-lookup"><span data-stu-id="acce9-118">Description</span></span>|  
|-----------|-----------------|  
|`yes`|<span data-ttu-id="acce9-119">게시자 정책을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-119">Applies publisher policy.</span></span> <span data-ttu-id="acce9-120">이것이 기본 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-120">This is the default setting.</span></span>|  
|`no`|<span data-ttu-id="acce9-121">게시자 정책을 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-121">Does not apply publisher policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="acce9-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="acce9-122">Child Elements</span></span>  
 <span data-ttu-id="acce9-123">없음</span><span class="sxs-lookup"><span data-stu-id="acce9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="acce9-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="acce9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="acce9-125">요소</span><span class="sxs-lookup"><span data-stu-id="acce9-125">Element</span></span>|<span data-ttu-id="acce9-126">설명</span><span class="sxs-lookup"><span data-stu-id="acce9-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="acce9-127">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="acce9-128">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acce9-129">설명</span><span class="sxs-lookup"><span data-stu-id="acce9-129">Remarks</span></span>  
 <span data-ttu-id="acce9-130">구성 요소 공급 업체를 새 버전의 어셈블리를 놓으면 공급 업체 이제 이전 버전을 사용 하는 응용 프로그램의 새 버전을 사용 하므로 게시자 정책 파일은 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-130">When a component vendor releases a new version of an assembly, the vendor can include a publisher policy so applications that use the old version now use the new version.</span></span> <span data-ttu-id="acce9-131">특정 어셈블리에 대 한 게시자 정책을 적용할지 여부를 지정 하려면는  **\<l i c y >** 요소에는  **\<dependentAssembly >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-131">To specify whether to apply publisher policy for a particular assembly, put the **\<publisherPolicy>** element in the **\<dependentAssembly>** element.</span></span>  
  
 <span data-ttu-id="acce9-132">에 대 한 기본 설정은 **적용** 특성은 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-132">The default setting for the **apply** attribute is **yes**.</span></span> <span data-ttu-id="acce9-133">설정의 **적용** 특성을 **없습니다** 이전 재정의 **예** 어셈블리에 대 한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-133">Setting the **apply** attribute to **no** overrides any previous **yes** settings for an assembly.</span></span>  
  
 <span data-ttu-id="acce9-134">권한이 명시적으로 사용 하 여 게시자 정책을 무시 하려면 응용 프로그램에 대 한 필요는 [ \<예 = "no" / >](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 응용 프로그램 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-134">Permission is required for an application to explicitly ignore publisher policy using the [\<publisherPolicy apply="no"/>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element in the application configuration file.</span></span> <span data-ttu-id="acce9-135">설정 하 여 권한 부여는 <xref:System.Security.Permissions.SecurityPermissionFlag> 에 플래그는 <xref:System.Security.Permissions.SecurityPermission>합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-135">The permission is granted by setting the <xref:System.Security.Permissions.SecurityPermissionFlag> flag on the <xref:System.Security.Permissions.SecurityPermission>.</span></span> <span data-ttu-id="acce9-136">자세한 내용은 참조 [어셈블리 바인딩 리디렉션 보안 권한](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-136">For more information, see [Assembly Binding Redirection Security Permission](../../../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="acce9-137">예제</span><span class="sxs-lookup"><span data-stu-id="acce9-137">Example</span></span>  
 <span data-ttu-id="acce9-138">다음 예에서는 어셈블리에 대 한 게시자 정책을 해제 `myAssembly`합니다.</span><span class="sxs-lookup"><span data-stu-id="acce9-138">The following example turns off publisher policy for the assembly, `myAssembly`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="acce9-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="acce9-139">See Also</span></span>  
 [<span data-ttu-id="acce9-140">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="acce9-140">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="acce9-141">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="acce9-141">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="acce9-142">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="acce9-142">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="acce9-143">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="acce9-143">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
