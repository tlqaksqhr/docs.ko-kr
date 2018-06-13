---
title: '&lt;NetFx40_LegacySecurityPolicy&gt; 요소'
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d9312d25842ccfcdf84e678d34b9bfde3fe7dd0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753985"
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a><span data-ttu-id="15fad-102">&lt;NetFx40_LegacySecurityPolicy&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="15fad-102">&lt;NetFx40_LegacySecurityPolicy&gt; Element</span></span>
<span data-ttu-id="15fad-103">런타임이 레거시 CAS(코드 액세스 보안) 정책을 사용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-103">Specifies whether the runtime uses legacy code access security (CAS) policy.</span></span>  
  
 <span data-ttu-id="15fad-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="15fad-104">\<configuration></span></span>  
<span data-ttu-id="15fad-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="15fad-105">\<runtime></span></span>  
<span data-ttu-id="15fad-106">< NetFx40_LegacySecurityPolicy ></span><span class="sxs-lookup"><span data-stu-id="15fad-106"><NetFx40_LegacySecurityPolicy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15fad-107">구문</span><span class="sxs-lookup"><span data-stu-id="15fad-107">Syntax</span></span>  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15fad-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="15fad-108">Attributes and Elements</span></span>  
 <span data-ttu-id="15fad-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15fad-110">특성</span><span class="sxs-lookup"><span data-stu-id="15fad-110">Attributes</span></span>  
  
|<span data-ttu-id="15fad-111">특성</span><span class="sxs-lookup"><span data-stu-id="15fad-111">Attribute</span></span>|<span data-ttu-id="15fad-112">설명</span><span class="sxs-lookup"><span data-stu-id="15fad-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="15fad-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="15fad-114">런타임이 레거시 CAS 정책을 사용 하는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-114">Specifies whether the runtime uses legacy CAS policy.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="15fad-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="15fad-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="15fad-116">값</span><span class="sxs-lookup"><span data-stu-id="15fad-116">Value</span></span>|<span data-ttu-id="15fad-117">설명</span><span class="sxs-lookup"><span data-stu-id="15fad-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="15fad-118">런타임이 레거시 CAS 정책을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-118">The runtime does not use legacy CAS policy.</span></span> <span data-ttu-id="15fad-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="15fad-120">런타임이 레거시 CAS 정책을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-120">The runtime uses legacy CAS policy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="15fad-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="15fad-121">Child Elements</span></span>  
 <span data-ttu-id="15fad-122">없음</span><span class="sxs-lookup"><span data-stu-id="15fad-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15fad-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="15fad-123">Parent Elements</span></span>  
  
|<span data-ttu-id="15fad-124">요소</span><span class="sxs-lookup"><span data-stu-id="15fad-124">Element</span></span>|<span data-ttu-id="15fad-125">설명</span><span class="sxs-lookup"><span data-stu-id="15fad-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="15fad-126">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="15fad-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15fad-128">설명</span><span class="sxs-lookup"><span data-stu-id="15fad-128">Remarks</span></span>  
 <span data-ttu-id="15fad-129">.NET Framework 버전 3.5 및 이전 버전에서는 CAS 정책을 항상 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-129">In the .NET Framework version 3.5 and earlier versions, CAS policy is always in effect.</span></span> <span data-ttu-id="15fad-130">에 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS 정책을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-130">In the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS policy must be enabled.</span></span>  
  
 <span data-ttu-id="15fad-131">CAS 정책에는 버전 별로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-131">CAS policy is version-specific.</span></span> <span data-ttu-id="15fad-132">이전 버전의.NET Framework에 존재 하는 CAS 정책을 사용자 지정에서 없게 해야 합니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-132">Custom CAS policies that exist in earlier versions of the .NET Framework must be respecified in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].</span></span>  
  
 <span data-ttu-id="15fad-133">적용 된 `<NetFx40_LegacySecurityPolicy>` 요소를 한 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 어셈블리에 영향을 주지 않습니다 [보안 투명 코드](../../../../../docs/framework/misc/security-transparent-code.md); 투명도 규칙이 계속 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-133">Applying the `<NetFx40_LegacySecurityPolicy>` element to a [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] assembly does not affect [security-transparent code](../../../../../docs/framework/misc/security-transparent-code.md); the transparency rules still apply.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15fad-134">적용 된 `<NetFx40_LegacySecurityPolicy>` 요소에서 만든 네이티브 이미지 어셈블리에 대 한 성능이 크게 저하 될 수 있습니다는 [네이티브 이미지 생성기 (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) 에 설치 되어 있지는 [전역 어셈블리 캐시 ](../../../../../docs/framework/app-domains/gac.md).</span><span class="sxs-lookup"><span data-stu-id="15fad-134">Applying the `<NetFx40_LegacySecurityPolicy>` element can result in significant performance penalties for native image assemblies created by the [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) that are not installed in the [global assembly cache](../../../../../docs/framework/app-domains/gac.md).</span></span> <span data-ttu-id="15fad-135">성능 저하는 특성이 적용 되는 때로 네이티브 이미지 어셈블리를 로드 해야 런타임 없을 때 발생, 될 같이-just-in-time 어셈블리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-135">The performance degradation is caused by the inability of the runtime to load the assemblies as native images when the attribute is applied, resulting in their being loaded as just-in-time assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15fad-136">이전 대상.NET Framework 버전을 지정 하는 경우는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Visual Studio 프로젝트에 대 한 프로젝트 설정에서 CAS 정책을 활성화 되며 해당 버전에 대해 지정 된 사용자 지정 CAS 정책을 포함 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-136">If you specify a target .NET Framework version that is earlier than the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the project settings for your Visual Studio project, CAS policy will be enabled, including any custom CAS policies you specified for that version.</span></span> <span data-ttu-id="15fad-137">그러나 됩니다 new를 사용 하려면 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 형식 및 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-137">However, you will not be able to use new [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] types and members.</span></span> <span data-ttu-id="15fad-138">사용 하 여.NET Framework의 이전 버전을 지정할 수도 있습니다는 [ \<supportedRuntime > 요소](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 시작 설정 스키마에서의 프로그램 [응용 프로그램 구성 파일](../../../../../docs/framework/configure-apps/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-138">You can also specify an earlier version of the .NET Framework by using the [\<supportedRuntime> element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in the startup settings schema in your [application configuration file](../../../../../docs/framework/configure-apps/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15fad-139">구성 파일의 구문은 대/소문자 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-139">Configuration file syntax is case-sensitive.</span></span> <span data-ttu-id="15fad-140">구문 및 예제 섹션에 제공 된 구문을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-140">You should use the syntax as provided in the Syntax and Example sections.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="15fad-141">구성 파일</span><span class="sxs-lookup"><span data-stu-id="15fad-141">Configuration File</span></span>  
 <span data-ttu-id="15fad-142">이 요소는 응용 프로그램 구성 파일에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-142">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15fad-143">예제</span><span class="sxs-lookup"><span data-stu-id="15fad-143">Example</span></span>  
 <span data-ttu-id="15fad-144">다음 예제에서는 응용 프로그램에 대 한 레거시 CAS 정책을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15fad-144">The following example shows how to enable legacy CAS policy for an application.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="15fad-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15fad-145">See Also</span></span>  
 [<span data-ttu-id="15fad-146">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="15fad-146">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="15fad-147">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="15fad-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
