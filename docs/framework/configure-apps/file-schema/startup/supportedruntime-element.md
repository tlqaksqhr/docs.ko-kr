---
title: "&lt;supportedRuntime&gt; 요소"
ms.date: 10/17/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 77886cef1a8dbd320223526b86f86fa9cee6a9f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltsupportedruntimegt-element"></a><span data-ttu-id="b9ad0-102">&lt;supportedRuntime&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="b9ad0-102">&lt;supportedRuntime&gt; Element</span></span>
<span data-ttu-id="b9ad0-103">응용 프로그램이 지원하는 공용 언어 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-103">Specifies which versions of the common language runtime the application supports.</span></span> <span data-ttu-id="b9ad0-104">이 요소는 .NET Framework 1.1 이상 버전으로 작성된 모든 응용 프로그램에서 사용되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-104">This element should be used by all applications built with version 1.1 or later of the .NET Framework.</span></span>  
  
[<span data-ttu-id="b9ad0-105">\<구성></span><span class="sxs-lookup"><span data-stu-id="b9ad0-105">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  

[<span data-ttu-id="b9ad0-106">\<startup></span><span class="sxs-lookup"><span data-stu-id="b9ad0-106">\<startup></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)  
  
<span data-ttu-id="b9ad0-107">**\<supportedRuntime>**</span><span class="sxs-lookup"><span data-stu-id="b9ad0-107">**\<supportedRuntime>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ad0-108">구문</span><span class="sxs-lookup"><span data-stu-id="b9ad0-108">Syntax</span></span>  
  
```xml  
<supportedRuntime version="runtime version" sku="sku id"/>  
```  
  
## <a name="attributes"></a><span data-ttu-id="b9ad0-109">특성</span><span class="sxs-lookup"><span data-stu-id="b9ad0-109">Attributes</span></span>  
  
|<span data-ttu-id="b9ad0-110">특성</span><span class="sxs-lookup"><span data-stu-id="b9ad0-110">Attribute</span></span>|<span data-ttu-id="b9ad0-111">설명</span><span class="sxs-lookup"><span data-stu-id="b9ad0-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9ad0-112">**version**</span><span class="sxs-lookup"><span data-stu-id="b9ad0-112">**version**</span></span>|<span data-ttu-id="b9ad0-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b9ad0-114">응용 프로그램이 지원하는 공용 언어 런타임(CLR) 버전을 지정하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-114">A string value that specifies the version of the common language runtime (CLR) that this application supports.</span></span> <span data-ttu-id="b9ad0-115">유효한 값에 대해서는 `version` 특성을 참조 하십시오.는 ["런타임 버전" 값](#version) 섹션.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-115">For valid values of the `version` attribute, see the ["runtime version" values](#version) section.</span></span> <span data-ttu-id="b9ad0-116">**참고:** 통해.NET Framework 3.5는 "*런타임 버전*" 형식으로 지정 *주요*. *사소한*. *빌드*합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-116">**Note:**  Through the .NET Framework 3.5, the "*runtime version*" value takes the form *major*.*minor*.*build*.</span></span> <span data-ttu-id="b9ad0-117">[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]부터는 주 및 부 버전 번호만 필요합니다(즉, "v4.0.30319"가 아니라 "v4.0"만 필요).</span><span class="sxs-lookup"><span data-stu-id="b9ad0-117">Beginning with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], only the major and minor version numbers are required (that is, "v4.0" instead of "v4.0.30319").</span></span> <span data-ttu-id="b9ad0-118">짧은 문자열이 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-118">The shorter string is recommended.</span></span>|  
|<span data-ttu-id="b9ad0-119">**sku**</span><span class="sxs-lookup"><span data-stu-id="b9ad0-119">**sku**</span></span>|<span data-ttu-id="b9ad0-120">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b9ad0-121">이 응용 프로그램이 지원하는 .NET Framework 버전을 지정하는 SKU(Stock Keeping Unit)를 지정하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-121">A string value that specifies the stock-keeping unit (SKU), which in turn specifies which .NET Framework release this application supports.</span></span><br /><br /> <span data-ttu-id="b9ad0-122">.NET Framework 4.0의 사용으로 시작 된 `sku` 특성을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-122">Starting with the .NET Framework 4.0, the use of the `sku` attribute is recommended.</span></span>  <span data-ttu-id="b9ad0-123">존재한다면 앱이 대상으로 하는 .NET Framework의 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-123">When present, it indicates the version of the .NET Framework that the app targets.</span></span><br /><br /> <span data-ttu-id="b9ad0-124">Sku 특성의 유효한 값에 대 한 참조는 ["sku id" 값](#sku) 섹션.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-124">For valid values of the sku attribute, see the ["sku id" values](#sku) section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9ad0-125">설명</span><span class="sxs-lookup"><span data-stu-id="b9ad0-125">Remarks</span></span>  
<span data-ttu-id="b9ad0-126">경우는  **\<supportedRuntime >** 요소가 응용 프로그램 구성 파일에 없다면, 응용 프로그램을 작성 하는 데 런타임 버전이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-126">If the **\<supportedRuntime>** element is not present in the application configuration file, the version of the runtime used to build the application is used.</span></span>  

<span data-ttu-id="b9ad0-127"> **\<supportedRuntime >** 요소는 버전 1.1 이상 런타임에 사용 하 여 빌드된 모든 응용 프로그램에서 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-127">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="b9ad0-128">런타임 버전 1.0만 지원 하도록 작성 된 응용 프로그램을 사용 해야 합니다는 [ \<requiredRuntime >](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-128">Applications built to support only version 1.0 of the runtime must use the [\<requiredRuntime>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md) element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9ad0-129">사용 하는 경우는 [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) 구성 파일을 지정 하려면 함수를 사용 해야 합니다는 `<requiredRuntime>` 모든 버전의 런타임에 대 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-129">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="b9ad0-130">`<supportedRuntime>` 사용할 때 요소는 무시 됩니다 [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-130">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
<span data-ttu-id="b9ad0-131">.NET Framework 1.1~3.5의 런타임 버전을 지원하는 앱의 경우 여러 버전의 런타임이 지원되면 첫 번째 요소는 우선 순위가 가장 높은 런타임 버전을 지정하고 마지막 요소는 우선 순위가 가장 낮은 버전을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-131">For apps that support versions of the runtime from the .NET Framework 1.1 through 3.5, when multiple versions of the runtime are supported, the first element should specify the most preferred version of the runtime, and the last element should specify the least preferred version.</span></span> <span data-ttu-id="b9ad0-132">.NET Framework 4.0 또는 이상 버전에서 지 원하는 앱에 대 한는 `version` .NET Framework 4 이상 버전에 공통적으로 적용 되는 CLR 버전을 나타내는 특성 및 `sku` 특성 단일.NET Framework 버전을 나타내는 하는 응용 프로그램 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-132">For apps that support the .NET Framework 4.0 or later versions, the `version` attribute indicates the CLR version, which is common to the .NET Framework 4 and later versions, and the `sku` attribute indicates single .NET Framework version that the app targets.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9ad0-133">응용 프로그램 같은 레거시 활성화 경로 사용 하는 경우는 [CorBindToRuntimeEx 함수](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), 이전 버전에서 clr 버전 4를 활성화 하려면 이러한 경로 중이 고 응용 프로그램의 경우또는[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]종속 되어 있지만 이전 버전의.NET Framework로 빌드된 혼합 모드 어셈블리에 것으로 부족 지정 하는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 지원 되는 런타임 목록에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-133">If your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework, it is not sufficient to specify the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in the list of supported runtimes.</span></span> <span data-ttu-id="b9ad0-134">또한,는 [ \<시작 > 요소](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 프로그램 구성 파일에 설정 해야 합니다는 `useLegacyV2RuntimeActivationPolicy` 특성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-134">In addition, in the [\<startup> element](../../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in your configuration file, you must set the `useLegacyV2RuntimeActivationPolicy` attribute to `true`.</span></span> <span data-ttu-id="b9ad0-135">그러나 이 특성을 `true`로 설정하면 .NET Framework의 이전 버전으로 빌드된 모든 구성 요소가 빌드 시 사용된 런타임 대신 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]을(를) 사용하여 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-135">However, setting this attribute to `true` means that all components built with earlier versions of the .NET Framework are run using the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] instead of the runtimes they were built with.</span></span>  
  
<span data-ttu-id="b9ad0-136">실행할 수 있는 모든 .NET Framework 버전을 사용하여 응용 프로그램을 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-136">We recommend that you test applications with all the .NET Framework versions that they can run on.</span></span>  
  
<a name="version"></a>   
## <a name="runtime-version-values"></a><span data-ttu-id="b9ad0-137">"런타임 버전" 값</span><span class="sxs-lookup"><span data-stu-id="b9ad0-137">"runtime version" values</span></span>  
<span data-ttu-id="b9ad0-138">`runtime` 특성 지정된 된 응용 프로그램에 필요한 공용 언어 런타임 (CLR) 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-138">The `runtime` attribute specifies the Common Language Runtime (CLR) version that is required for a given application.</span></span> <span data-ttu-id="b9ad0-139">모든.NET Framework v4.x 버전을 지정 하는 `v4.0` CLR.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-139">Note that all .NET Framework v4.x versions specify the `v4.0` CLR.</span></span> <span data-ttu-id="b9ad0-140">다음 표에서 유효한 값에 대 한는 *런타임 버전* 의 값은 `version` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-140">The following table lists valid values for the *runtime version* value of the `version` attribute.</span></span>  

|<span data-ttu-id="b9ad0-141">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="b9ad0-141">.NET Framework version</span></span>|<span data-ttu-id="b9ad0-142">`version` 특성</span><span class="sxs-lookup"><span data-stu-id="b9ad0-142">`version` attribute</span></span>|  
|----------------------------|-------------------------|  
|<span data-ttu-id="b9ad0-143">1.0</span><span class="sxs-lookup"><span data-stu-id="b9ad0-143">1.0</span></span>|<span data-ttu-id="b9ad0-144">"v1.0.3705"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-144">"v1.0.3705"</span></span>|  
|<span data-ttu-id="b9ad0-145">1.1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-145">1.1</span></span>|<span data-ttu-id="b9ad0-146">"v1.1.4322"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-146">"v1.1.4322"</span></span>|  
|<span data-ttu-id="b9ad0-147">2.0</span><span class="sxs-lookup"><span data-stu-id="b9ad0-147">2.0</span></span>|<span data-ttu-id="b9ad0-148">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-148">"v2.0.50727"</span></span>|  
|<span data-ttu-id="b9ad0-149">3.0</span><span class="sxs-lookup"><span data-stu-id="b9ad0-149">3.0</span></span>|<span data-ttu-id="b9ad0-150">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-150">"v2.0.50727"</span></span>|  
|<span data-ttu-id="b9ad0-151">3.5</span><span class="sxs-lookup"><span data-stu-id="b9ad0-151">3.5</span></span>|<span data-ttu-id="b9ad0-152">"v2.0.50727"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-152">"v2.0.50727"</span></span>|  
|<span data-ttu-id="b9ad0-153">4.0-4.7.1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-153">4.0-4.7.1</span></span>|<span data-ttu-id="b9ad0-154">"v4.0"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-154">"v4.0"</span></span>|  

  
<a name="sku"></a>   
## <a name="sku-id-values"></a><span data-ttu-id="b9ad0-155">"sku id" 값</span><span class="sxs-lookup"><span data-stu-id="b9ad0-155">"sku id" values</span></span>  
<span data-ttu-id="b9ad0-156">`sku` 특성 대상 프레임 워크 모니커 (TFM)를 사용 하 여 앱을 대상으로 하 고 실행 하는 데 필요한.NET Framework의 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-156">The `sku` attribute uses a target framework moniker (TFM) to indicate the version of the .NET Framework that the app targets and requires to run.</span></span> <span data-ttu-id="b9ad0-157">지원 되는 유효한 값을 나열 하는 다음 표에서 `sku` 특성,.NET Framework 4로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-157">The following table lists valid values that are supported by the `sku` attribute, starting with the .NET Framework 4.</span></span>
  
|<span data-ttu-id="b9ad0-158">.NET Framework 버전</span><span class="sxs-lookup"><span data-stu-id="b9ad0-158">.NET Framework version</span></span>|<span data-ttu-id="b9ad0-159">`sku` 특성</span><span class="sxs-lookup"><span data-stu-id="b9ad0-159">`sku` attribute</span></span>|  
|----------------------------|---------------------|  
|<span data-ttu-id="b9ad0-160">4.0</span><span class="sxs-lookup"><span data-stu-id="b9ad0-160">4.0</span></span>|<span data-ttu-id="b9ad0-161">".NETFramework,Version=v4.0"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-161">".NETFramework,Version=v4.0"</span></span>|  
|<span data-ttu-id="b9ad0-162">4.0, Client Profile</span><span class="sxs-lookup"><span data-stu-id="b9ad0-162">4.0, Client Profile</span></span>|<span data-ttu-id="b9ad0-163">".NETFramework,Version=v4.0,Profile=Client"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-163">".NETFramework,Version=v4.0,Profile=Client"</span></span>|  
|<span data-ttu-id="b9ad0-164">4.0, 플랫폼 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-164">4.0, platform update 1</span></span>|<span data-ttu-id="b9ad0-165">.NETFramework,Version=v4.0.1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-165">.NETFramework,Version=v4.0.1</span></span>|  
|<span data-ttu-id="b9ad0-166">4.0, Client Profile, 업데이트 1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-166">4.0, Client Profile, update 1</span></span>|<span data-ttu-id="b9ad0-167">.NETFramework,Version=v4.0.1,Profile=Client</span><span class="sxs-lookup"><span data-stu-id="b9ad0-167">.NETFramework,Version=v4.0.1,Profile=Client</span></span>|  
|<span data-ttu-id="b9ad0-168">4.0, 플랫폼 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="b9ad0-168">4.0, platform update 2</span></span>|<span data-ttu-id="b9ad0-169">.NETFramework,Version=v4.0.2</span><span class="sxs-lookup"><span data-stu-id="b9ad0-169">.NETFramework,Version=v4.0.2</span></span>|  
|<span data-ttu-id="b9ad0-170">4.0, Client Profile, 업데이트 2</span><span class="sxs-lookup"><span data-stu-id="b9ad0-170">4.0, Client Profile, update 2</span></span>|<span data-ttu-id="b9ad0-171">.NETFramework,Version=v4.0.2,Profile=Client</span><span class="sxs-lookup"><span data-stu-id="b9ad0-171">.NETFramework,Version=v4.0.2,Profile=Client</span></span>|  
|<span data-ttu-id="b9ad0-172">4.0, 플랫폼 업데이트 3</span><span class="sxs-lookup"><span data-stu-id="b9ad0-172">4.0, platform update 3</span></span>|<span data-ttu-id="b9ad0-173">.NETFramework,Version=v4.0.3</span><span class="sxs-lookup"><span data-stu-id="b9ad0-173">.NETFramework,Version=v4.0.3</span></span>|  
|<span data-ttu-id="b9ad0-174">4.0, Client Profile, 업데이트 3</span><span class="sxs-lookup"><span data-stu-id="b9ad0-174">4.0, Client Profile, update 3</span></span>|<span data-ttu-id="b9ad0-175">.NETFramework,Version=v4.0.3,Profile=Client</span><span class="sxs-lookup"><span data-stu-id="b9ad0-175">.NETFramework,Version=v4.0.3,Profile=Client</span></span>|  
|<span data-ttu-id="b9ad0-176">4.5</span><span class="sxs-lookup"><span data-stu-id="b9ad0-176">4.5</span></span>|<span data-ttu-id="b9ad0-177">".NETFramework,Version=v4.5"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-177">".NETFramework,Version=v4.5"</span></span>|  
|<span data-ttu-id="b9ad0-178">4.5.1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-178">4.5.1</span></span>|<span data-ttu-id="b9ad0-179">".NETFramework,Version=v4.5.1"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-179">".NETFramework,Version=v4.5.1"</span></span>|  
|<span data-ttu-id="b9ad0-180">4.5.2</span><span class="sxs-lookup"><span data-stu-id="b9ad0-180">4.5.2</span></span>|<span data-ttu-id="b9ad0-181">".NETFramework,Version=v4.5.2"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-181">".NETFramework,Version=v4.5.2"</span></span>|  
|<span data-ttu-id="b9ad0-182">4.6</span><span class="sxs-lookup"><span data-stu-id="b9ad0-182">4.6</span></span>|<span data-ttu-id="b9ad0-183">".NETFramework,Version=v4.6"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-183">".NETFramework,Version=v4.6"</span></span>|  
|<span data-ttu-id="b9ad0-184">4.6.1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-184">4.6.1</span></span>|<span data-ttu-id="b9ad0-185">".NETFramework,Version=v4.6.1"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-185">".NETFramework,Version=v4.6.1"</span></span>|  
|<span data-ttu-id="b9ad0-186">4.6.2</span><span class="sxs-lookup"><span data-stu-id="b9ad0-186">4.6.2</span></span>|<span data-ttu-id="b9ad0-187">". NETFramework, Version = v4.6.2 "</span><span class="sxs-lookup"><span data-stu-id="b9ad0-187">".NETFramework,Version=v4.6.2"</span></span>|  
|<span data-ttu-id="b9ad0-188">4.7</span><span class="sxs-lookup"><span data-stu-id="b9ad0-188">4.7</span></span>|<span data-ttu-id="b9ad0-189">". NETFramework, Version = v4.7 "</span><span class="sxs-lookup"><span data-stu-id="b9ad0-189">".NETFramework,Version=v4.7"</span></span>|
|<span data-ttu-id="b9ad0-190">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b9ad0-190">4.7.1</span></span>|<span data-ttu-id="b9ad0-191">". NETFramework, Version = 4.7.1"</span><span class="sxs-lookup"><span data-stu-id="b9ad0-191">".NETFramework,Version=4.7.1"</span></span>|

## <a name="example"></a><span data-ttu-id="b9ad0-192">예</span><span class="sxs-lookup"><span data-stu-id="b9ad0-192">Example</span></span>  
 <span data-ttu-id="b9ad0-193">다음 예제에서는 구성 파일에 지원되는 런타임 버전을 지정하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-193">The following example shows how to specify the supported runtime version in a configuration file.</span></span> <span data-ttu-id="b9ad0-194">구성 파일은 응용 프로그램에.NET Framework 4.7 대상으로 지정 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-194">The configuration file indicates that the app targets the .NET Framework 4.7.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />  
   </startup>  
</configuration>  
```  
  
## <a name="configuration-file"></a><span data-ttu-id="b9ad0-195">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b9ad0-195">Configuration File</span></span>  
 <span data-ttu-id="b9ad0-196">이 요소는 응용 프로그램 구성 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ad0-196">This element can be used in the application configuration file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ad0-197">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9ad0-197">See Also</span></span>  
 [<span data-ttu-id="b9ad0-198">시작 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b9ad0-198">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="b9ad0-199">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b9ad0-199">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="b9ad0-200">In-Process Side-by-Side 실행</span><span class="sxs-lookup"><span data-stu-id="b9ad0-200">In-Process Side-by-Side Execution</span></span>](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
