---
title: "&lt;loadFromRemoteSources&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efb968d40e54c7552fba0a592e759f9e83c92309
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltloadfromremotesourcesgt-element"></a><span data-ttu-id="34bbb-102">&lt;loadFromRemoteSources&gt; 요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-102">&lt;loadFromRemoteSources&gt; Element</span></span>
<span data-ttu-id="34bbb-103">부여할지 여부를 원격 원본에서 어셈블리가 완전 신뢰를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-103">Specifies whether assemblies from remote sources should be granted full trust.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34bbb-104">Visual Studio 프로젝트의 오류 목록 또는 빌드 오류가 오류 메시지로 인해이 항목에 연결 하 고 된 경우 참조 [하는 방법: Visual Studio에서 웹의 어셈블리를 사용 하 여](http://msdn.microsoft.com/en-us/d8635b63-89a0-41aa-90f4-f351b2111070)합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-104">If you were directed to this topic because of an error message in the Visual Studio project error list or a build error, see [How to: Use an Assembly from the Web in Visual Studio](http://msdn.microsoft.com/en-us/d8635b63-89a0-41aa-90f4-f351b2111070).</span></span>  
  
 <span data-ttu-id="34bbb-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="34bbb-105">\<configuration></span></span>  
<span data-ttu-id="34bbb-106">\<런타임 ></span><span class="sxs-lookup"><span data-stu-id="34bbb-106">\<runtime></span></span>  
<span data-ttu-id="34bbb-107">\<loadFromRemoteSources ></span><span class="sxs-lookup"><span data-stu-id="34bbb-107">\<loadFromRemoteSources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34bbb-108">구문</span><span class="sxs-lookup"><span data-stu-id="34bbb-108">Syntax</span></span>  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34bbb-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="34bbb-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34bbb-111">특성</span><span class="sxs-lookup"><span data-stu-id="34bbb-111">Attributes</span></span>  
  
|<span data-ttu-id="34bbb-112">특성</span><span class="sxs-lookup"><span data-stu-id="34bbb-112">Attribute</span></span>|<span data-ttu-id="34bbb-113">설명</span><span class="sxs-lookup"><span data-stu-id="34bbb-113">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="34bbb-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="34bbb-115">부여할지 여부를 원격 원본에서 로드 된 어셈블리가 완전 신뢰를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-115">Specifies whether an assembly that is loaded from remote sources should be granted full trust.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="34bbb-116">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="34bbb-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="34bbb-117">값</span><span class="sxs-lookup"><span data-stu-id="34bbb-117">Value</span></span>|<span data-ttu-id="34bbb-118">설명</span><span class="sxs-lookup"><span data-stu-id="34bbb-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="34bbb-119">원격 원본에서 응용 프로그램에 완전 신뢰를 부여 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="34bbb-119">Do not grant full trust to applications from remote sources.</span></span> <span data-ttu-id="34bbb-120">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="34bbb-121">원격 원본에서 응용 프로그램에 완전 신뢰를 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-121">Grant full trust to applications from remote sources.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34bbb-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-122">Child Elements</span></span>  
 <span data-ttu-id="34bbb-123">없음</span><span class="sxs-lookup"><span data-stu-id="34bbb-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34bbb-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-124">Parent Elements</span></span>  
  
|<span data-ttu-id="34bbb-125">요소</span><span class="sxs-lookup"><span data-stu-id="34bbb-125">Element</span></span>|<span data-ttu-id="34bbb-126">설명</span><span class="sxs-lookup"><span data-stu-id="34bbb-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34bbb-127">공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="34bbb-128">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34bbb-129">설명</span><span class="sxs-lookup"><span data-stu-id="34bbb-129">Remarks</span></span>  
 <span data-ttu-id="34bbb-130">.NET Framework 버전 3.5 및 이전 버전에서 원격 위치에서 어셈블리를 로드 하는 경우 어셈블리가 실행 로드 된 영역에 의존 하는 권한 부여 집합으로 부분적으로 신뢰 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-130">In the .NET Framework version 3.5 and earlier versions, if you loaded an assembly from a remote location, the assembly would run partially trusted with a grant set that depended on the zone in which it was loaded.</span></span> <span data-ttu-id="34bbb-131">예를 들어, 웹 사이트에서 어셈블리를 로드한 경우 인터넷 영역으로 로드되고 Internet 권한 집합을 부여 받습니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-131">For example, if you loaded an assembly from a website, it was loaded into the Internet zone and granted the Internet permission set.</span></span> <span data-ttu-id="34bbb-132">즉, 인터넷 샌드박스에서 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-132">In other words, it executed in an Internet sandbox.</span></span> <span data-ttu-id="34bbb-133">해당 어셈블리를 실행 하려고 하는 경우는 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] 및 이상 버전에서 예외가 발생; 어셈블리에 대 한 샌드박스를 명시적으로 만들 하거나 해야 합니다 (참조 [하는 방법: 부분적으로 신뢰할 수 있는 코드 실행 샌드박스에서](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), 또는 완전 신뢰에서 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-133">If you try to run that assembly in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] and later versions, an exception is thrown; you must either explicitly create a sandbox for the assembly (see [How to: Run Partially Trusted Code in a Sandbox](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)), or run it in full trust.</span></span>  
  
 <span data-ttu-id="34bbb-134">`<loadFromRemoteSources>` 요소를 사용하면 이전 버전의 .NET Framework에서 부분 신뢰로 실행되었던 어셈블리가 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상 버전에서 완전 신뢰로 실행되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-134">The `<loadFromRemoteSources>` element lets you specify that the assemblies that would have run partially trusted in earlier versions of the .NET Framework are to be run fully trusted in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="34bbb-135">기본적으로, 원격 어셈블리는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상에서 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-135">By default, remote assemblies do not run in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later.</span></span> <span data-ttu-id="34bbb-136">원격 어셈블리를 실행하려면, 완전 신뢰로 실행하거나 원격 어셈블리를 실행할 샌드박스가 적용된 <xref:System.AppDomain>을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-136">To run a remote assembly, you must either run it as fully trusted or create a sandboxed <xref:System.AppDomain> in which to run it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34bbb-137">[!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)]에서 로컬 네트워크 공유에 있는 어셈블리는 기본적으로 완전 신뢰 상태로 실행되고, `<loadFromRemoteSources>` 요소를 활성화할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-137">In the [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)], assemblies on local network shares are run as full trust by default; you do not have to enable the `<loadFromRemoteSources>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34bbb-138">응용 프로그램을 웹에서 복사한 경우, Windows에서는 해당 프로그램이 로컬 컴퓨터에 있더라도 웹 응용 프로그램이라는 플래그가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-138">If an application has been copied from the web, it is flagged by Windows as being a web application, even if it resides on the local computer.</span></span> <span data-ttu-id="34bbb-139">파일 속성을 변경 하 여 해당 지정을 변경 하거나 사용할 수 있습니다는 `<loadFromRemoteSources>` 완전 신뢰 어셈블리에 부여할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-139">You can change that designation by changing the file properties, or you can use the `<loadFromRemoteSources>` element to grant the assembly full trust.</span></span> <span data-ttu-id="34bbb-140">또는 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 메서드를 사용하여 운영 체제가 웹에서 로드되었음을 표시하는 로컬 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-140">As an alternative, you can use the <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> method to load a local assembly that the operating system has flagged as having been loaded from the web.</span></span>  
  
 <span data-ttu-id="34bbb-141">`enabled` 특성이이 요소는 코드 액세스 보안 (CA)를 사용 하지 않도록 설정 하는 경우에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-141">The `enabled` attribute for this element is effective only when code access security (CAS) is disabled.</span></span> <span data-ttu-id="34bbb-142">기본적으로 CAS 정책에 사용할 수 없습니다는 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 이상 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-142">By default, CAS policy is disabled in the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later versions.</span></span> <span data-ttu-id="34bbb-143">설정한 경우 `enabled` 를 `true`, 원격 응용 프로그램에 완전 신뢰가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-143">If you set `enabled` to `true`, remote applications are granted full trust.</span></span>  
  
 <span data-ttu-id="34bbb-144">경우 `<loadFromRemoteSources>``enabled` 로 설정 되지 않은 `true`, 다음과 같은 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-144">If `<loadFromRemoteSources>``enabled` is not set to `true`, an exception is thrown under the following conditions:</span></span>  
  
-   <span data-ttu-id="34bbb-145">현재 도메인의 샌드 박싱 동작에서의 동작과에서 차이가 있는 [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-145">The sandboxing behavior of the current domain is different from its behavior in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span> <span data-ttu-id="34bbb-146">CAS 정책을 사용 하지 않도록 설정할 고 샌드박스 아니어야 현재 도메인에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-146">This requires CAS policy to be disabled, and the current domain not to be sandboxed.</span></span>  
  
-   <span data-ttu-id="34bbb-147">로드 되는 어셈블리에서 가져오지 않았습니다 고 `MyComputer` 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-147">The assembly being loaded is not from the `MyComputer` zone.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34bbb-148">발생할 수 있습니다는 <xref:System.IO.FileLoadException> 호스팅 컴퓨터에서 연결 된 폴더에서 파일을 로드 하려고 할 때 Windows Virtual PC 응용 프로그램에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-148">You may get a <xref:System.IO.FileLoadException> in a Windows Virtual PC application when you try to load a file from linked folders on the hosting computer.</span></span> <span data-ttu-id="34bbb-149">통해 연결 된 폴더에서 파일을 로드 하려고 할 때에이 오류가 발생할 [원격 데스크톱 서비스](http://go.microsoft.com/fwlink/?LinkId=182775) (터미널 서비스).</span><span class="sxs-lookup"><span data-stu-id="34bbb-149">This error may also occur when you try to load a file from a folder linked over [Remote Desktop Services](http://go.microsoft.com/fwlink/?LinkId=182775) (Terminal Services).</span></span> <span data-ttu-id="34bbb-150">예외를 방지 하려면 설정 `enabled` 를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-150">To avoid the exception, set `enabled` to `true`.</span></span>  
  
 <span data-ttu-id="34bbb-151">설정의 `<loadFromRemoteSources>` 요소를 `true` 이 예외가 throw 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-151">Setting the `<loadFromRemoteSources>` element to `true` prevents this exception from being thrown.</span></span> <span data-ttu-id="34bbb-152">있는지 있습니다 의존 하지 않고 sandbox에 공용 언어 런타임 보안을 위해 로드 된 어셈블리를 지정할 수 있도록 하 고 실행 되도록 지정할 수 완전 신뢰 합니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-152">It enables you to specify that you are not relying on the common language runtime to sandbox the loaded assemblies for security, and that they can be allowed to execute as full trust.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="34bbb-153">완전 신뢰 어셈블리를 실행 해서는 안, 경우에이 구성 요소를 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="34bbb-153">If the assembly should not run in full trust, do not set this configuration element.</span></span> <span data-ttu-id="34bbb-154">대신는 샌드박스를 만들 <xref:System.AppDomain> 를 로드할 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-154">Instead, create a sandboxed <xref:System.AppDomain> in which to load the assembly.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="34bbb-155">구성 파일</span><span class="sxs-lookup"><span data-stu-id="34bbb-155">Configuration File</span></span>  
 <span data-ttu-id="34bbb-156">이 요소는 일반적으로 응용 프로그램 구성 파일에서 사용하지만 컨텍스트에 따라 다른 구성 파일에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-156">This element is typically used in the application configuration file, but can be used in other configuration files depending upon the context.</span></span> <span data-ttu-id="34bbb-157">자세한 내용은 문서 참조 [자세한 암시적 사용의 CAS 정책: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) .NET 보안 블로그에서.</span><span class="sxs-lookup"><span data-stu-id="34bbb-157">For more information, see the article [More Implicit Uses of CAS Policy: loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) in the .NET Security blog.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34bbb-158">예</span><span class="sxs-lookup"><span data-stu-id="34bbb-158">Example</span></span>  
 <span data-ttu-id="34bbb-159">다음 예에서는 원격 원본에서 응용 프로그램에 완전 신뢰를 부여 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="34bbb-159">The following example shows how to grant full trust to applications from remote sources.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="34bbb-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34bbb-160">See Also</span></span>  
 [<span data-ttu-id="34bbb-161">CAS 정책의 암시적 더 용도: loadFromRemoteSources</span><span class="sxs-lookup"><span data-stu-id="34bbb-161">More Implicit Uses of CAS Policy: loadFromRemoteSources</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [<span data-ttu-id="34bbb-162">방법: 샌드박스에서 부분적으로 신뢰할 수 있는 코드 실행</span><span class="sxs-lookup"><span data-stu-id="34bbb-162">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="34bbb-163">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="34bbb-163">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="34bbb-164">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="34bbb-164">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
