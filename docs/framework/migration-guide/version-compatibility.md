---
title: ".NET Framework의 버전 호환성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework, version compatibility
- .NET Framework 4.5, compatibility with earlier versions
- .NET Framework versions, compatibility
ms.assetid: 2f25e522-456a-48c3-8a53-e5f39275649f
caps.latest.revision: 35
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 741c2d1c49f44a6a7b299845cdc37cc8425c326b
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="version-compatibility-in-the-net-framework"></a><span data-ttu-id="3d032-102">.NET Framework의 버전 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-102">Version Compatibility in the .NET Framework</span></span>
<span data-ttu-id="3d032-103">이전 버전과의 호환성은 특정 버전의 플랫폼용으로 개발된 앱이 해당 플랫폼의 다음 버전에서도 실행되는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-103">Backward compatibility means that an app that was developed for a particular version of a platform will run on later versions of that platform.</span></span> <span data-ttu-id="3d032-104">.NET Framework에서는 이전 버전과의 호환성을 최대한 지원하려고 합니다. 한 버전의 .NET Framework용으로 작성된 소스 코드는 다음 버전의 .NET Framework에서 컴파일되어야 하며 한 버전의 .NET Framework에서 실행되는 이진 파일은 다음 버전의 .NET Framework에서 동일하게 작동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-104">The .NET Framework tries to maximize backward compatibility: Source code written for one version of the .NET Framework should compile on later versions of the .NET Framework, and binaries that run on one version of the .NET Framework should behave identically on later versions of the .NET Framework.</span></span>  
  
<a name="Apps"></a>   
## <a name="version-compatibility-for-apps"></a><span data-ttu-id="3d032-105">앱의 버전 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-105">Version compatibility for apps</span></span>  
 <span data-ttu-id="3d032-106">기본적으로 앱은 빌드에 사용된 .NET Framework 버전에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-106">By default, an app runs on the version of the .NET Framework that it was built for.</span></span> <span data-ttu-id="3d032-107">해당 버전이 없고 앱 구성 파일에 지원되는 버전이 정의되지 않은 경우 .NET Framework 초기화 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-107">If that version is not present and the app configuration file does not define supported versions, a .NET Framework initialization error may occur.</span></span> <span data-ttu-id="3d032-108">이 경우 앱을 실행하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-108">In this case, the attempt to run the app will fail.</span></span>  
  
 <span data-ttu-id="3d032-109">앱이 실행되는 특정 버전을 정의하려면 하나 이상의 [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 요소를 앱의 구성 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-109">To define the specific versions on which your app runs, add one or more [\<supportedRuntime>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) elements to your app's configuration file.</span></span> <span data-ttu-id="3d032-110">각 `<supportedRuntime>` 요소에는 지원되는 런타임 버전이 나열됩니다. 우선 순위가 가장 높은 버전이 처음에 지정되고 우선 순위가 가장 낮은 버전이 마지막에 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-110">Each `<supportedRuntime>` element lists a supported version of the runtime, with the first specifying the most preferred version and the last specifying the least preferred version.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <supportedRuntime version="v2.0.50727" />  
      <supportedRuntime version="v4.0" />  
   </startup>  
</configuration>  
```  
  
 <span data-ttu-id="3d032-111">자세한 내용은 [방법: .NET Framework 4 또는 4.x를 지원하도록 앱 구성](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d032-111">For more information, see [How to: Configure an App to Support .NET Framework 4 or 4.x](../../../docs/framework/migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md).</span></span>  
  
## <a name="version-compatibility-for-components"></a><span data-ttu-id="3d032-112">구성 요소의 버전 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-112">Version compatibility for components</span></span>  
 <span data-ttu-id="3d032-113">앱에서는 실행되는 .NET Framework의 버전을 자체적으로 제어할 수 있지만, 구성 요소는 제어할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-113">An app can control the version of the .NET Framework on which it runs, but a component cannot.</span></span> <span data-ttu-id="3d032-114">구성 요소 및 클래스 라이브러리는 특정 앱의 컨텍스트에서 로드되므로 앱이 실행되는 .NET Framework 버전에서 자동으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-114">Components and class libraries are loaded in the context of a particular app, and therefore automatically run on the version of the .NET Framework that the app runs on.</span></span>  
  
 <span data-ttu-id="3d032-115">이러한 제한 사항 때문에 구성 요소에서 호환성 보장은 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-115">Because of this restriction, compatibility guarantees are especially important for components.</span></span> <span data-ttu-id="3d032-116">.NET Framework 4부터 <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=fullName> 특성을 해당 구성 요소에 적용하여 구성 요소가 여러 버전 간 호환성을 유지해야 하는 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-116">Starting with the .NET Framework 4, you can specify the degree to which a component is expected to remain compatible across multiple versions by applying the <xref:System.Runtime.Versioning.ComponentGuaranteesAttribute?displayProperty=fullName> attribute to that component.</span></span> <span data-ttu-id="3d032-117">여러 도구에서는 이 특성을 사용하여 이후 버전의 구성 요소에서 호환성 보장을 잠재적으로 위반할 수 있는 가능성을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-117">Tools can use this attribute to detect potential violations of the compatibility guarantee in future versions of a component.</span></span>  
  
## <a name="backward-compatibility-and-the-net-framework-45"></a><span data-ttu-id="3d032-118">이전 버전과의 호환성과 .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="3d032-118">Backward compatibility and the .NET Framework 4.5</span></span>  
 <span data-ttu-id="3d032-119">.NET Framework 4.5 및 해당 포인트 릴리스(4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2 및 4.7)는 이전 버전의 .NET Framework로 빌드된 앱과 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-119">The .NET Framework 4.5 and its point releases (4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, and 4.7) are backward-compatible with apps that were built with earlier versions of the .NET Framework.</span></span> <span data-ttu-id="3d032-120">즉, 이전 버전으로 빌드된 앱과 구성 요소는 수정하지 않아도 .NET Framework 4.5에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-120">In other words, apps and components built with previous versions will work without modification on the .NET Framework 4.5.</span></span> <span data-ttu-id="3d032-121">그러나 앱은 기본적으로 해당 앱을 위해 개발된 공용 언어 런타임 버전에서 실행되기 때문에 .NET Framework 4.5에서 앱을 실행하려면 구성 파일을 제공해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-121">However, by default, apps run on the version of the common language runtime for which they were developed, so you may have to provide a configuration file to enable your app to run on the .NET Framework 4.5.</span></span> <span data-ttu-id="3d032-122">자세한 내용은 이 문서 앞부분의 [앱의 버전 호환성](#Apps) 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d032-122">For more information, see the [Version compatibility for apps](#Apps) section earlier in this article.</span></span>  
  
 <span data-ttu-id="3d032-123">실제 상황에서 .NET Framework의 외견상 중요하지 않은 변경 사항 및 프로그래밍 기술 변경 사항에 의해 이 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-123">In practice, this compatibility can be broken by seemingly inconsequential changes in the .NET Framework and changes in programming techniques.</span></span> <span data-ttu-id="3d032-124">예를 들어 .NET Framework 4.5 성능 향상 기능이 이전 버전에서 발생하지 않은 경합 상태를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-124">For example, performance improvements in the .NET Framework 4.5 can expose a race condition that did not occur on earlier versions.</span></span> <span data-ttu-id="3d032-125">마찬가지로 .NET Framework 어셈블리에 하드 코드된 경로 사용, 특정 버전의 .NET Framework와 같음 비교 수행, 리플렉션을 사용한 전용 필드 값 가져오기는 이전 버전과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-125">Similarly, using a hard-coded path to .NET Framework assemblies, performing an equality comparison with a particular version of the .NET Framework, and getting the value of a private field by using reflection are not backward-compatible practices.</span></span> <span data-ttu-id="3d032-126">또한 각 .NET Framework 버전에는 일부 앱 및 구성 요소의 호환성에 영향을 줄 수 있는 버그 수정 내용 및 보안 관련 변경 사항이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-126">In addition, each version of the .NET Framework includes bug fixes and security-related changes that can affect the compatibility of some apps and components.</span></span>  
  
 <span data-ttu-id="3d032-127">앱이나 구성 요소가 .NET Framework 4.5 및 해당 포인트 릴리스([!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2 또는 4.7)에서 제대로 작동하지 않는 경우 다음 검사 목록을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-127">If your app or component does not work as expected on the .NET Framework 4.5 (including its point releases, the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)], 4.5.2, 4.6, 4.6.1, 4.6.2, or 4.7, use the following checklists:</span></span>  
  
-   <span data-ttu-id="3d032-128">이러한 항목에 대해 앱에 영향을 줄 수 있는 모든 변경 사항을 확인하고 설명된 해결 방법을 적용하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d032-128">Check these topics  for any changes that might affect your app and apply the workaround described:</span></span>  
  
    -   [<span data-ttu-id="3d032-129">.NET Framework 4 마이그레이션 문제</span><span class="sxs-lookup"><span data-stu-id="3d032-129">.NET Framework 4 Migration Issues</span></span>](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)  
  
    -   [<span data-ttu-id="3d032-130">4.5의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-130">Application Compatibility in 4.5</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5.md)  
  
    -   [<span data-ttu-id="3d032-131">4.5.1의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-131">Application Compatibility in 4.5.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-1.md)  
  
    -   [<span data-ttu-id="3d032-132">4.5.2의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-132">Application Compatibility in 4.5.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-5-2.md)  
  
    -   [<span data-ttu-id="3d032-133">4.6의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-133">Application Compatibility in 4.6</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6.md)  
  
    -   [<span data-ttu-id="3d032-134">4.6.1의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-134">Application Compatibility in 4.6.1</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)  
  
    -   [<span data-ttu-id="3d032-135">4.6.2의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-135">Application Compatibility in 4.6.2</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)  

    - [<span data-ttu-id="3d032-136">4.7의 응용 프로그램 호환성</span><span class="sxs-lookup"><span data-stu-id="3d032-136">Application Compatibility in 4.7</span></span>](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-2.md)
       
-   <span data-ttu-id="3d032-137">.NET Framework 1.1 앱이 있는 경우 다음 항목도 검토하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d032-137">If you have a .NET Framework 1.1 app, also review these topics:</span></span>  
  
    -   [<span data-ttu-id="3d032-138">.NET Framework 2.0의 변경 내용</span><span class="sxs-lookup"><span data-stu-id="3d032-138">Changes in .NET Framework 2.0</span></span>](http://go.microsoft.com/fwlink/?LinkID=125263)  
  
    -   [<span data-ttu-id="3d032-139">.NET Framework 3.5 SP1의 변경 내용</span><span class="sxs-lookup"><span data-stu-id="3d032-139">Changes in .NET Framework 3.5 SP1</span></span>](http://go.microsoft.com/fwlink/?LinkId=186989)  
  
-   <span data-ttu-id="3d032-140">.NET Framework 4.5 또는 해당 포인트 릴리스에서 실행하기 위해 기존 소스 코드를 다시 컴파일하거나 기존 소스 코드 기반의 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 대상으로 하는 새 버전의 앱 또는 구성 요소를 개발하는 경우 [클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md)에서 사용되지 않는 형식과 멤버를 확인하고 설명된 해결 방법을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-140">If you are recompiling existing source code to run on the .NET Framework 4.5 or its point releases, or if you are developing a new version of an app or component that targets the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] from an existing source code base, check [What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md) for obsolete types and members, and apply the workaround described.</span></span> <span data-ttu-id="3d032-141">이전에 컴파일된 코드는 사용되지 않는 것으로 표시된 형식과 멤버에 대해 계속해서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-141">(Previously compiled code will continue to run against types and members that have been marked as obsolete.)</span></span>  
  
-   <span data-ttu-id="3d032-142">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]가 변경되어 앱이 깨지는 것으로 확인된 경우 [런타임 설정 스키마](../../../docs/framework/configure-apps/file-schema/runtime/index.md)에서 앱 구성 파일의 런타임 설정을 사용하여 이전 동작을 복원할 수 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-142">If you determine that a change in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] has broken your app, check the [Runtime Settings Schema](../../../docs/framework/configure-apps/file-schema/runtime/index.md) to determine whether you can use a runtime setting in your app's configuration file to restore the previous behavior.</span></span>  
  
-   <span data-ttu-id="3d032-143">문서화되지 않은 문제가 발생한 경우 [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815)에 버그를 등록하고 해당 버그 번호로 [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com)에 문의하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d032-143">If you encounter an issue that is not documented, file a [Microsoft Connect](http://go.microsoft.com/fwlink/?LinkID=154815) bug and contact [netfxcf@microsoft.com](mailto:netfxcf@microsoft.com) with the bug number.</span></span>  
  
## <a name="compatibility-and-side-by-side-execution"></a><span data-ttu-id="3d032-144">호환성 및 Side-By-Side 실행</span><span class="sxs-lookup"><span data-stu-id="3d032-144">Compatibility and side-by-side execution</span></span>  
 <span data-ttu-id="3d032-145">문제에 대한 적합한 해결 방법을 찾지 못한 경우 .NET Framework 4.5(또는 해당 포인트 릴리스 중 하나)가 버전 1.1, 2.0 및 3.5와 side-by-side 실행된다는 것과 버전 4.5는 버전 4를 대체하는 내부 업데이트임을 기억하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d032-145">If you cannot find a suitable workaround for your issue, remember that the .NET Framework 4.5 (or one of its point releases) runs side by side with versions 1.1, 2.0, and 3.5, and is an in-place update that replaces version 4.</span></span> <span data-ttu-id="3d032-146">버전 1.1, 2.0 및 3.5를 대상으로 하는 앱의 경우 대상 컴퓨터에 적절한 .NET Framework 버전을 설치하여 앱을 가장 적합한 환경에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d032-146">For apps that target versions 1.1, 2.0, and 3.5, you can install the appropriate version of the .NET Framework on the target machine to run the app in its best environment.</span></span> <span data-ttu-id="3d032-147">Side-by-Side 실행에 대한 자세한 내용은 [Side-by-Side 실행](../../../docs/framework/deployment/side-by-side-execution.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3d032-147">For more information about side-by-side execution, see [Side-by-Side Execution](../../../docs/framework/deployment/side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d032-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d032-148">See Also</span></span>  
 <span data-ttu-id="3d032-149">[새로운 기능](../../../docs/framework/whats-new/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d032-149">[What's New](../../../docs/framework/whats-new/index.md) </span></span>  
 <span data-ttu-id="3d032-150">[클래스 라이브러리의 사용되지 않는 기능](../../../docs/framework/whats-new/whats-obsolete.md) </span><span class="sxs-lookup"><span data-stu-id="3d032-150">[What's Obsolete in the Class Library](../../../docs/framework/whats-new/whats-obsolete.md) </span></span>  
 <span data-ttu-id="3d032-151">[응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="3d032-151">[Application Compatibility](../../../docs/framework/migration-guide/application-compatibility.md) </span></span>  
 <span data-ttu-id="3d032-152">[Microsoft .NET Framework 지원 기간 정책](http://go.microsoft.com/fwlink/p/?LinkId=248212) </span><span class="sxs-lookup"><span data-stu-id="3d032-152">[Microsoft .NET Framework Support Lifecycle Policy](http://go.microsoft.com/fwlink/p/?LinkId=248212) </span></span>  
 [<span data-ttu-id="3d032-153">.NET Framework 4 마이그레이션 문제</span><span class="sxs-lookup"><span data-stu-id="3d032-153">.NET Framework 4 Migration Issues</span></span>](../../../docs/framework/migration-guide/net-framework-4-migration-issues.md)

