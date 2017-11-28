---
title: "&lt;disableFusionUpdatesFromADManager&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4aa3343e7f3f60bbf6a57340d858c1ef12197bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a><span data-ttu-id="c5f67-102">&lt;disableFusionUpdatesFromADManager&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="c5f67-102">&lt;disableFusionUpdatesFromADManager&gt; Element</span></span>
<span data-ttu-id="c5f67-103">런타임 호스트가 응용 프로그램 도메인에 대한 구성 설정을 재정의할 수 있도록 허용하는 기본 동작을 사용하지 않도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="c5f67-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="c5f67-104">\<configuration> Element</span></span>  
<span data-ttu-id="c5f67-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="c5f67-105">\<runtime> Element</span></span>  
<span data-ttu-id="c5f67-106">\<disableFusionUpdatesFromADManager ></span><span class="sxs-lookup"><span data-stu-id="c5f67-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5f67-107">구문</span><span class="sxs-lookup"><span data-stu-id="c5f67-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5f67-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c5f67-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c5f67-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5f67-110">특성</span><span class="sxs-lookup"><span data-stu-id="c5f67-110">Attributes</span></span>  
  
|<span data-ttu-id="c5f67-111">특성</span><span class="sxs-lookup"><span data-stu-id="c5f67-111">Attribute</span></span>|<span data-ttu-id="c5f67-112">설명</span><span class="sxs-lookup"><span data-stu-id="c5f67-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5f67-113">사용</span><span class="sxs-lookup"><span data-stu-id="c5f67-113">enabled</span></span>|<span data-ttu-id="c5f67-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c5f67-115">Fusion 설정을 재정의 하는 기본 기능 되지 않는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c5f67-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="c5f67-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="c5f67-117">값</span><span class="sxs-lookup"><span data-stu-id="c5f67-117">Value</span></span>|<span data-ttu-id="c5f67-118">설명</span><span class="sxs-lookup"><span data-stu-id="c5f67-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c5f67-119">0</span><span class="sxs-lookup"><span data-stu-id="c5f67-119">0</span></span>|<span data-ttu-id="c5f67-120">Fusion 설정을 재정의 하는 기능을 해제 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="c5f67-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="c5f67-121">이 기본적으로 시작 된 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-121">This is the default behavior, starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
|<span data-ttu-id="c5f67-122">1</span><span class="sxs-lookup"><span data-stu-id="c5f67-122">1</span></span>|<span data-ttu-id="c5f67-123">Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="c5f67-124">이 이전 버전의.NET Framework의 동작으로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5f67-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c5f67-125">Child Elements</span></span>  
 <span data-ttu-id="c5f67-126">없음</span><span class="sxs-lookup"><span data-stu-id="c5f67-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5f67-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c5f67-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c5f67-128">요소</span><span class="sxs-lookup"><span data-stu-id="c5f67-128">Element</span></span>|<span data-ttu-id="c5f67-129">설명</span><span class="sxs-lookup"><span data-stu-id="c5f67-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c5f67-130">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c5f67-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5f67-132">설명</span><span class="sxs-lookup"><span data-stu-id="c5f67-132">Remarks</span></span>  
 <span data-ttu-id="c5f67-133">부터는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], 기본 동작은 허용 하는 <xref:System.AppDomainManager> 개체를 사용 하 여 구성 설정을 재정의 하는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성 또는 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 의 메서드는 <xref:System.AppDomainSetup> 구현에 전달 되는 개체 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 의 서브 클래스에서 메서드 <xref:System.AppDomainManager>합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-133">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="c5f67-134">기본 응용 프로그램 도메인에 대 한 설정을 변경 하면 응용 프로그램 구성 파일에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="c5f67-135">에 전달 된 구성 설정을 재정의 하는 다른 응용 프로그램 도메인에 대해서는 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="c5f67-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="c5f67-136">새 구성 정보를 전달 하거나 null을 전달할 수 있습니다 (`Nothing` Visual basic에서)에서 전달 된 구성 정보를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="c5f67-137">구성 정보를 둘 다에 전달 하지 마십시오는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성 및 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="c5f67-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="c5f67-138">둘 다에 구성 정보를 전달 하는 경우에 전달 하는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성이 무시 하기 때문에 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 응용 프로그램 구성 파일에서 구성 정보를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="c5f67-139">사용 하는 경우는 <xref:System.AppDomainSetup.ConfigurationFile%2A> 속성을 null을 전달할 수 (`Nothing` Visual basic에서)에 <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 구성에 대 한 호출에 지정 된 바이트를 제거 하는 메서드는 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> 또는 <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="c5f67-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="c5f67-140">구성 정보 외에도 다음 설정에서 변경할 수 있습니다는 <xref:System.AppDomainSetup> 구현에 전달 되는 개체는 <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 메서드: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, 및 <xref:System.AppDomainSetup.ShadowCopyFiles%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="c5f67-141">사용 하는 대신는 `<disableFusionUpdatesFromADManager>` 요소인 레지스트리 설정을 만들어 또는 환경 변수를 설정 하 여 기본 동작을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="c5f67-142">레지스트리에서 라는 DWORD 값을 만듭니다 `COMPLUS_disableFusionUpdatesFromADManager` 아래 `HKCU\Software\Microsoft\.NETFramework` 또는 `HKLM\Software\Microsoft\.NETFramework`, 값을 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="c5f67-143">명령줄에서 환경 변수 설정 `COMPLUS_disableFusionUpdatesFromADManager` 1입니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5f67-144">예제</span><span class="sxs-lookup"><span data-stu-id="c5f67-144">Example</span></span>  
 <span data-ttu-id="c5f67-145">다음 예제를 사용 하 여 Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 하는 방법을 보여 줍니다는 `<disableFusionUpdatesFromADManager>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c5f67-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5f67-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5f67-146">See Also</span></span>  
 [<span data-ttu-id="c5f67-147">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c5f67-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="c5f67-148">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c5f67-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="c5f67-149">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="c5f67-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
