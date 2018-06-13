---
title: 어셈블리 버전 리디렉션
ms.date: 03/30/2017
helpviewer_keywords:
- assembly binding, redirection
- redirecting assembly binding to earlier version
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], binding redirection
ms.assetid: 88fb1a17-6ac9-4b57-8028-193aec1f727c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 3459ebd2f1df38ac70e9211fd4865e227cd996cb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759272"
---
# <a name="redirecting-assembly-versions"></a><span data-ttu-id="634bc-102">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="634bc-102">Redirecting Assembly Versions</span></span>
<span data-ttu-id="634bc-103">.NET Framework 어셈블리, 타사 어셈블리 또는 고유의 앱 어셈블리로 컴파일 타임 바인딩 참조를 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-103">You can redirect compile-time binding references to .NET Framework assemblies, third-party assemblies, or your own app's assemblies.</span></span> <span data-ttu-id="634bc-104">게시자 정책, 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일 등을 통한 다양한 방법으로 여러 버전의 어셈블리를 사용하도록 응용 프로그램을 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-104">You can redirect your app to use a different version of an assembly in a number of ways: through publisher policy, through an app configuration file; or through the machine configuration file.</span></span> <span data-ttu-id="634bc-105">이 문서에서는 .NET Framework에서 어셈블리 바인딩의 작동 방식과 구성 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-105">This article discusses how assembly binding works in the .NET Framework and how it can be configured.</span></span>  
  
<a name="BKMK_Assemblyunificationanddefaultbinding"></a>   
## <a name="assembly-unification-and-default-binding"></a><span data-ttu-id="634bc-106">어셈블리 통합 및 기본 바인딩</span><span class="sxs-lookup"><span data-stu-id="634bc-106">Assembly unification and default binding</span></span>  
 <span data-ttu-id="634bc-107">.NET Framework 어셈블리에 대한 바인딩은 *어셈블리 통합*이라고 하는 프로세스를 통해 리디렉션되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-107">Bindings to .NET Framework assemblies are sometimes redirected through a process called *assembly unification*.</span></span> <span data-ttu-id="634bc-108">.NET Framework는 공용 언어 런타임 버전과 형식 라이브러리를 구성하는 약 24개의 .NET Framework 어셈블리로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-108">The .NET Framework consists of a version of the common language runtime and about two dozen .NET Framework assemblies that make up the type library.</span></span> <span data-ttu-id="634bc-109">이러한 .NET Framework 어셈블리는 런타임에서 하나의 단위로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-109">These .NET Framework assemblies are treated by the runtime as a single unit.</span></span> <span data-ttu-id="634bc-110">기본적으로, 응용 프로그램이 시작되면 런타임으로 실행되는 코드의 형식에 대한 모든 참조는 프로세스에서 로드되는 런타임과 버전 번호가 같은 .NET Framework 어셈블리로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-110">By default, when an app is launched, all references to types in code run by the runtime are directed to .NET Framework assemblies that have the same version number as the runtime that is loaded in a process.</span></span> <span data-ttu-id="634bc-111">이 모델에서 발생하는 리디렉션은 런타임에 대한 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-111">The redirections that occur with this model are the default behavior for the runtime.</span></span>  
  
 <span data-ttu-id="634bc-112">예를 들어 응용 프로그램에서 System.XML 네임스페이스의 형식을 참조하고 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]를 사용하여 빌드된 경우, 런타임 버전 4.5와 함께 제공되는 System.XML 어셈블리에 대한 정적 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-112">For example, if your app references types in the System.XML namespace and was built by using the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], it contains static references to the System.XML assembly that ships with runtime version 4.5.</span></span> <span data-ttu-id="634bc-113">.NET Framework 4와 함께 제공되는 System.XML 어셈블리를 가리키도록 바인딩 참조를 리디렉션하려는 경우에는 응용 프로그램 구성 파일에 리디렉션 정보를 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-113">If you want to redirect the binding reference to point to the System.XML assembly that ship with the .NET Framework 4, you can put redirect information in the app configuration file.</span></span> <span data-ttu-id="634bc-114">통합된 .NET Framework 어셈블리에 대한 구성 파일에서 바인딩 리디렉션은 해당 어셈블리에 대한 통합을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-114">A binding redirection in a configuration file for a unified .NET Framework assembly cancels the unification for that assembly.</span></span>  
  
 <span data-ttu-id="634bc-115">또한 여러 버전을 사용할 수 있는 경우 타사 어셈블리에 대해 어셈블리 바인딩을 수동으로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-115">In addition, you may want to manually redirect assembly binding for third-party assemblies if there are multiple versions available.</span></span>  
  
<a name="BKMK_Redirectingassemblyversionsbyusingpublisherpolicy"></a>   
## <a name="redirecting-assembly-versions-by-using-publisher-policy"></a><span data-ttu-id="634bc-116">게시자 정책을 사용하여 어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="634bc-116">Redirecting assembly versions by using publisher policy</span></span>  
 <span data-ttu-id="634bc-117">어셈블리 공급업체는 새 어셈블리와 함께 게시자 정책 파일을 포함하여 최신 버전의 어셈블리로 응용 프로그램을 유도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-117">Vendors of assemblies can direct apps to a newer version of an assembly by including a publisher policy file with the new assembly.</span></span> <span data-ttu-id="634bc-118">전역 어셈블리 캐시에 있는 게시자 정책 파일에는 어셈블리 리디렉션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-118">The publisher policy file, which is located in the global assembly cache, contains assembly redirection settings.</span></span>  
  
 <span data-ttu-id="634bc-119">각 *주*.*부* 버전의 어셈블리에는 자체 게시자 정책 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-119">Each *major*.*minor* version of an assembly has its own publisher policy file.</span></span> <span data-ttu-id="634bc-120">예를 들어 버전 2.0.2.222에서 2.0.3.000으로 리디렉션과 버전 2.0.2.321에서 2.0.3.000으로 리디렉션은 버전 2.0과 연관되기 때문에 동일한 파일로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-120">For example, redirections from version 2.0.2.222 to 2.0.3.000 and from version 2.0.2.321 to version 2.0.3.000 both go into the same file, because they are associated with version 2.0.</span></span> <span data-ttu-id="634bc-121">그러나 버전 3.0.0.999에서 4.0.0.000으로 리디렉션은 버전 3.0.999용 파일로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-121">However, a redirection from version 3.0.0.999 to version 4.0.0.000 goes into the file for version 3.0.999.</span></span> <span data-ttu-id="634bc-122">.NET Framework의 각 주 버전에는 자체 게시자 정책 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-122">Each major version of the .NET Framework has its own publisher policy file.</span></span>  
  
 <span data-ttu-id="634bc-123">어셈블리에 대한 게시자 정책 파일이 있으면, 런타임에서 어셈블리의 매니페스트 및 응용 프로그램 구성 파일을 확인한 후 이 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-123">If a publisher policy file exists for an assembly, the runtime checks this file after checking the assembly's manifest and app configuration file.</span></span> <span data-ttu-id="634bc-124">공급업체는 새 어셈블리가 리디렉션되는 어셈블리와 역호환되는 경우에만 게시자 정책 파일을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-124">Vendors should use publisher policy files only when the new assembly is backward compatible with the assembly being redirected.</span></span>  
  
 <span data-ttu-id="634bc-125">[게시자 정책 무시 섹션](#bypass_PP)에 설명된 대로, 앱 구성 파일에서 설정을 지정하여 응용 프로그램의 게시자 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-125">You can bypass publisher policy for your app by specifying settings in the app configuration file, as discussed in the [Bypassing publisher policy section](#bypass_PP).</span></span>  
  
<a name="BKMK_Redirectingassemblyversionsattheapplevel"></a>   
## <a name="redirecting-assembly-versions-at-the-app-level"></a><span data-ttu-id="634bc-126">앱 수준에서 어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="634bc-126">Redirecting assembly versions at the app level</span></span>  
 <span data-ttu-id="634bc-127">앱 구성 파일을 통해 앱의 바인딩 동작을 변경하는 몇 가지 방법이 있습니다. 즉, 파일을 수동으로 편집하거나, 자동 바인딩 리디렉션을 사용하거나, 게시자 정책을 무시하여 바인딩 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-127">There are a few different techniques for changing the binding behavior for your app through the app configuration file: you can manually edit the file, you can rely on automatic binding redirection, or you can specify binding behavior by bypassing publisher policy.</span></span>  
  
### <a name="manually-editing-the-app-config-file"></a><span data-ttu-id="634bc-128">앱 프로그램 구성 파일을 수동으로 편집</span><span class="sxs-lookup"><span data-stu-id="634bc-128">Manually editing the app config file</span></span>  
 <span data-ttu-id="634bc-129">앱 프로그램 구성 파일을 수동으로 편집하여 어셈블리 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-129">You can manually edit the app configuration file to resolve assembly issues.</span></span> <span data-ttu-id="634bc-130">예를 들어, 공급업체가 게시자 정책을 제공하지 않고 앱에서 사용되는 어셈블리의 최신 버전을 출시하는 경우에는 역호환성이 보장되지 않으므로 다음과 같이 앱의 구성 파일에 어셈블리 바인딩 정보를 배치하여 새 버전의 어셈블리를 사용하도록 앱을 유도할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-130">For example, if a vendor might release a newer version of an assembly that your app uses without supplying a publisher policy, because they do not guarantee backward compatibility, you can direct your app to use the newer version of the assembly by putting assembly binding information in your app's configuration file as follows.</span></span>  
  
```xml  
<dependentAssembly>  
  <assemblyIdentity name="someAssembly"  
    publicKeyToken="32ab4ba45e0a69a1"  
    culture="en-us" />  
  <bindingRedirect oldVersion="7.0.0.0" newVersion="8.0.0.0" />  
</dependentAssembly>  
```  
  
### <a name="relying-on-automatic-binding-redirection"></a><span data-ttu-id="634bc-131">자동 바인딩 리디렉션 사용</span><span class="sxs-lookup"><span data-stu-id="634bc-131">Relying on automatic binding redirection</span></span>  
 <span data-ttu-id="634bc-132">[!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]부터는, [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] 을 대상으로 하는 새 데스크톱 앱에서 자동 바인딩 리디렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-132">Starting with [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)], new desktop apps that target the [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] use automatic binding redirection.</span></span> <span data-ttu-id="634bc-133">즉, 두 구성 요소가 강력한 이름의 동일한 어셈블리의 다른 버전을 참조하는 경우 런타임에서 출력 앱 구성 파일(app.config)에 최신 버전의 어셈블리에 바인딩 리디렉션을 자동으로 추가한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-133">This means that if two components reference different versions of the same strong-named assembly, the runtime automatically adds a binding redirection to the newer version of the assembly in the output app configuration (app.config) file.</span></span> <span data-ttu-id="634bc-134">이 리디렉션은 그 밖에 발생할 수 있는 어셈블리 통합을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-134">This redirection overrides the assembly unification that might otherwise take place.</span></span> <span data-ttu-id="634bc-135">소스 app.config 파일은 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-135">The source app.config file is not modified.</span></span> <span data-ttu-id="634bc-136">예를 들어, 앱에서 대역 외 .NET Framework 구성 요소를 직접 참조하지만 동일한 구성 요소의 이전 버전을 대상으로 하는 타사 라이브러리를 사용한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-136">For example, let's say that your app directly references an out-of-band .NET Framework component but uses a third-party library that targets an older version of the same component.</span></span> <span data-ttu-id="634bc-137">앱을 컴파일하면, 최신 버전의 구성 요소에 대한 바인딩 리디렉션이 포함되도록 출력 앱 구성 파일이 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-137">When you compile the app, the output app configuration file is modified to contain a binding redirection to the newer version of the component.</span></span> <span data-ttu-id="634bc-138">웹앱을 만드는 경우, 바인딩 충돌에 대한 빌드 경고가 표시된 후에 소스 웹 구성 파일에 필요한 바인딩 리디렉션을 추가할 수 있는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-138">If you create a web app, you receive a build warning regarding the binding conflict, which in turn, gives you the option to add the necessary binding redirect to the source web configuration file.</span></span>  
  
 <span data-ttu-id="634bc-139">컴파일 시에 소스 app.config 파일에 바인딩 리디렉션을 수동으로 추가하는 경우 [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] 는 추가된 바인딩 리디렉션을 기준으로 어셈블리를 통합하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-139">If you  manually add binding redirects to the source app.config file, at compile time, [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] tries to unify the assemblies based on the binding redirects you added.</span></span> <span data-ttu-id="634bc-140">예를 들어, 어셈블리에 대해 다음과 같은 바인딩 리디렉션을 삽입한다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-140">For example, let's say you insert the following binding redirect for an assembly:</span></span>  
  
 `<bindingRedirect oldVersion="3.0.0.0" newVersion="2.0.0.0" />`  
  
 <span data-ttu-id="634bc-141">앱에 있는 다른 프로젝트가 동일한 어셈블리의 버전 1.0.0.0을 참조하는 경우, 자동 바인딩 리디렉션은 다음 항목을 출력 app.config 파일에 추가하여 이 어셈블리의 2.0.0.0 버전에 앱이 통합되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-141">If another project in your app references version 1.0.0.0 of the same assembly, automatic binding redirection adds the following entry to the output app.config file so that the app is unified on version 2.0.0.0 of this assembly:</span></span>  
  
 `<bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />`  
  
 <span data-ttu-id="634bc-142">[!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)]에서 앱이 이전 버전의 .NET Framework를 대상으로 하는 경우 자동 바인딩 리디렉션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-142">You can enable automatic binding redirection if your app targets older versions of the .NET Framework in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)].</span></span> <span data-ttu-id="634bc-143">app.config 파일에서 모든 어셈블리에 대해 바인딩 리디렉션 정보를 제공하여 기본 동작을 재정의하거나 바인딩 리디렉션 기능을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-143">You can override this default behavior by providing binding redirection information in the app.config file for any assembly, or turn off the binding redirection feature.</span></span> <span data-ttu-id="634bc-144">이 기능을 설정 하거나 해제 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 자동 바인딩 리디렉션 사용 안 함 및 사용](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-144">For information about how to turn this feature on or off, see [How to: Enable and Disable Automatic Binding Redirection](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md).</span></span>  
  
<a name="bypass_PP"></a>   
### <a name="bypassing-publisher-policy"></a><span data-ttu-id="634bc-145">게시자 정책 무시</span><span class="sxs-lookup"><span data-stu-id="634bc-145">Bypassing publisher policy</span></span>  
 <span data-ttu-id="634bc-146">필요에 따라 앱 구성 파일에서 게시자 정책을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-146">You can override publisher policy in the app configuration file if necessary.</span></span> <span data-ttu-id="634bc-147">예를 들어, 역호환성이 있다고 하는 최신 버전의 어셈블리가 앱을 중단시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-147">For example, new versions of assemblies that claim to be backward compatible can still break an app.</span></span> <span data-ttu-id="634bc-148">게시자 정책을 무시 하려는 경우 추가 [ \<l i c y >](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) 요소는 [ \<dependentAssembly >](../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md) 응용 프로그램 구성 파일 및는 집합에서요소**적용** 특성을 **없습니다**를 덮어씁니다. 이전 **예** 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-148">If you want to bypass publisher policy, add a [\<publisherPolicy>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) element to the [\<dependentAssembly>](../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md) element in the app configuration file, and set the **apply** attribute to **no**, which overrides any previous **yes** settings.</span></span>  
  
 `<publisherPolicy apply="no" />`  
  
 <span data-ttu-id="634bc-149">사용자에 대해 실행 중인 앱을 유지하려면 게시자 정책을 무시할 수 있지만, 문제가 발생할 경우 어셈블리 공급업체에 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-149">Bypass publisher policy to keep your app running for your users, but make sure you report the problem to the assembly vendor.</span></span> <span data-ttu-id="634bc-150">어셈블리에 게시자 정책 파일이 있는 경우, 공급업체는 해당 어셈블리가 역호환되는지 확인하고 클라이언트에서 가능하면 최신 버전을 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-150">If an assembly has a publisher policy file, the vendor should make sure that the assembly is backward compatible and that clients can use the new version as much as possible.</span></span>  
  
<a name="BKMK_Redirectingassemblyversionsatthemachinelevel"></a>   
## <a name="redirecting-assembly-versions-at-the-machine-level"></a><span data-ttu-id="634bc-151">컴퓨터 수준에서 어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="634bc-151">Redirecting assembly versions at the machine level</span></span>  
 <span data-ttu-id="634bc-152">드문 경우이지만 시스템 관리자가 컴퓨터의 모든 앱에서 특정 버전의 어셈블리를 사용해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-152">There might be rare cases when a machine administrator wants all apps on a computer to use a specific version of an assembly.</span></span> <span data-ttu-id="634bc-153">예를 들어, 관리자는 모든 앱에서 보안 허점을 해결하는 특정 어셈블리 버전을 사용해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-153">For example, the administrator might want every app to use a particular assembly version, because that version fixes a security hole.</span></span> <span data-ttu-id="634bc-154">컴퓨터의 구성 파일에서 어셈블리가 리디렉션되면, 이전 버전을 사용하는 컴퓨터의 모든 앱이 새 버전을 사용하도록 유도됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-154">If an assembly is redirected in the machine's configuration file, all apps on that machine that use the old version will be directed to use the new version.</span></span> <span data-ttu-id="634bc-155">컴퓨터 구성 파일은 앱 구성 파일 및 게시자 정책 파일을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-155">The machine configuration file overrides the app configuration file and the publisher policy file.</span></span> <span data-ttu-id="634bc-156">이 파일은 %*런타임 설치 경로*%\Config 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-156">This file is located in the %*runtime install path*%\Config directory.</span></span> <span data-ttu-id="634bc-157">일반적으로 .NET Framework는 %drive%\Windows\Microsoft.NET\Framework 디렉터리에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-157">Typically, the .NET Framework is installed in the %drive%\Windows\Microsoft.NET\Framework directory.</span></span>  
  
<a name="BKMK_Specifyingassemblybindinginconfigurationfiles"></a>   
## <a name="specifying-assembly-binding-in-configuration-files"></a><span data-ttu-id="634bc-158">구성 파일에 어셈블리 바인딩 지정</span><span class="sxs-lookup"><span data-stu-id="634bc-158">Specifying assembly binding in configuration files</span></span>  
 <span data-ttu-id="634bc-159">동일한 XML 형식을 사용하여 앱 구성 파일, 컴퓨터 구성 파일 또는 게시자 정책 파일에 있는 바인딩 리디렉션을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-159">You use the same XML format to specify binding redirects whether it’s in the app configuration file, the machine configuration file, or the publisher policy file.</span></span> <span data-ttu-id="634bc-160">다른 어셈블리 버전 리디렉션를 사용 하 여는 [ \<bindingRedirect >](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-160">To redirect one assembly version to another, use the [\<bindingRedirect>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md) element.</span></span> <span data-ttu-id="634bc-161">**oldVersion** 특성은 단일 어셈블리 버전 또는 다양한 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-161">The **oldVersion** attribute can specify a single assembly version or a range of versions.</span></span> <span data-ttu-id="634bc-162">`newVersion` 특성은 단일 버전을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-162">The `newVersion` attribute should specify a single version.</span></span>  <span data-ttu-id="634bc-163">예를 들어, `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` 은 런타임에서 1.1.0.0 - 1.2.0.0 버전의 어셈블리 대신 2.0.0.0 버전을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-163">For example, `<bindingRedirect oldVersion="1.1.0.0-1.2.0.0" newVersion="2.0.0.0"/>` specifies that the runtime should use version 2.0.0.0 instead of the assembly versions between 1.1.0.0 and 1.2.0.0.</span></span>  
  
 <span data-ttu-id="634bc-164">다음 코드 예제는 다양한 바인딩 리디렉션 시나리오를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-164">The following code example demonstrates a variety of binding redirect scenarios.</span></span> <span data-ttu-id="634bc-165">이 예제에서는 `myAssembly`에 대해 다양한 버전의 리디렉션을 지정하고, `mySecondAssembly`에 대해 단일 바인딩 리디렉션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-165">The example specifies a redirect for a range of versions for `myAssembly`, and a single binding redirect for `mySecondAssembly`.</span></span> <span data-ttu-id="634bc-166">또한 이 예제에서는 게시자 정책 파일이 `myThirdAssembly`에 대한 바인딩 리디렉션을 재정의하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-166">The example also specifies that publisher policy file will not override the binding redirects for `myThirdAssembly`.</span></span>  
  
 <span data-ttu-id="634bc-167">문자열을 지정 해야 어셈블리를 바인딩하려면 ":-microsoft-: asm.v1"와 **xmlns** 특성에 [ \<assemblyBinding >](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-167">To bind an assembly, you must specify the string "urn:schemas-microsoft-com:asm.v1" with the **xmlns** attribute in the [\<assemblyBinding>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) tag.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
      <dependentAssembly>  
        <assemblyIdentity name="myAssembly"  
          publicKeyToken="32ab4ba45e0a69a1"  
          culture="en-us" />  
        <!-- Assembly versions can be redirected in app,   
          publisher policy, or machine configuration files. -->  
        <bindingRedirect oldVersion="1.0.0.0-2.0.0.0" newVersion="3.0.0.0" />  
      </dependentAssembly>  
  <dependentAssembly>  
        <assemblyIdentity name="mySecondAssembly"  
          publicKeyToken="32ab4ba45e0a69a1"  
          culture="en-us" />  
             <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0" />  
      </dependentAssembly>  
      <dependentAssembly>  
      <assemblyIdentity name="myThirdAssembly"  
        publicKeyToken="32ab4ba45e0a69a1"  
        culture="en-us" />  
        <!-- Publisher policy can be set only in the app   
          configuration file. -->  
        <publisherPolicy apply="no" />  
      </dependentAssembly>  
    </assemblyBinding>  
  </runtime>  
</configuration>  
```  
  
### <a name="limiting-assembly--bindings-to-a-specific-version"></a><span data-ttu-id="634bc-168">특정 버전에 대한 어셈블리 바인딩 제한</span><span class="sxs-lookup"><span data-stu-id="634bc-168">Limiting assembly  bindings to a specific version</span></span>  
 <span data-ttu-id="634bc-169">사용할 수는 **appliesTo** 특성에 [ \<assemblyBinding >](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) 특정 버전의.NET 어셈블리 바인딩 참조를 리디렉션하려는 응용 프로그램 구성 파일의 요소 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-169">You can use the **appliesTo** attribute on the [\<assemblyBinding>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) element in an app configuration file to redirect assembly binding references to a specific version of the .NET Framework.</span></span> <span data-ttu-id="634bc-170">이 선택적 특성은 .NET Framework 버전 번호를 사용하여 특성이 적용되는 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-170">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="634bc-171">**appliesTo** 특성이 지정되지 않으면 [\<assemblyBinding>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) 요소는 .NET Framework의 모든 버전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-171">If no **appliesTo** attribute is specified, the [\<assemblyBinding>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) element applies to all versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="634bc-172">예를 들어 .NET Framework 버전 3.5 어셈블리에 대한 어셈블리 바인딩을 리디렉션하려면 앱 구성 파일에 다음 XML 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-172">For example, to redirect assembly binding for a .NET Framework 3.5 assembly, you would include the following XML code in your app configuration file.</span></span>  
  
```xml  
<runtime>  
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1"   
    appliesTo="v3.5">  
    <dependentAssembly>   
      <!-- assembly information goes here -->  
    </dependentAssembly>  
  </assemblyBinding>  
</runtime>  
```  
  
 <span data-ttu-id="634bc-173">버전 순서대로 리디렉션 정보를 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-173">You should enter redirection information in version order.</span></span> <span data-ttu-id="634bc-174">예를 들어, .NET Framework 3.5 어셈블리에 대한 어셈블리 바인딩 리디렉션 정보를 입력한 후에 .NET Framework 4.5 어셈블리에 대한 해당 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-174">For example, enter assembly binding redirection information for .NET Framework 3.5 assemblies followed by .NET Framework 4.5 assemblies.</span></span> <span data-ttu-id="634bc-175">마지막으로 **appliesTo** 특성을 사용하지 않으므로 모든 .NET Framework 버전에 적용되는 .NET Framework 어셈블리 리디렉션에 대한 어셈블리 바인딩 리디렉션 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-175">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="634bc-176">리디렉션 시 충돌이 발생하면 구성 파일에서 일치하는 첫 번째 리디렉션 문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-176">If there is a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>  
  
 <span data-ttu-id="634bc-177">예를 들어 한 참조를 .NET Framework 버전 3.5 어셈블리로 리디렉션하고 다른 참조를 .NET Framework 버전 4 어셈블리로 리디렉션하려면 다음 의사 코드에 표시된 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="634bc-177">For example, to redirect one reference to a .NET Framework 3.5 assembly and another reference to a .NET Framework 4 assembly, use the pattern shown in the following pseudocode.</span></span>  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v3.5 ">   
  <!—.NET Framework version 3.5 redirects here -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="..." appliesTo="v4.0.30319">   
  <!—.NET Framework version 4.0 redirects here -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="...">   
  <!-- redirects meant for all versions of the runtime -->   
</assemblyBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="634bc-178">참고 항목</span><span class="sxs-lookup"><span data-stu-id="634bc-178">See Also</span></span>  
 [<span data-ttu-id="634bc-179">방법: 자동 바인딩 리디렉션 사용 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="634bc-179">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)  
 [<span data-ttu-id="634bc-180">\<bindingRedirect > 요소</span><span class="sxs-lookup"><span data-stu-id="634bc-180">\<bindingRedirect> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bindingredirect-element.md)  
 [<span data-ttu-id="634bc-181">어셈블리 바인딩 리디렉션 보안 권한</span><span class="sxs-lookup"><span data-stu-id="634bc-181">Assembly Binding Redirection Security Permission</span></span>](../../../docs/framework/configure-apps/assembly-binding-redirection-security-permission.md)  
 [<span data-ttu-id="634bc-182">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="634bc-182">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 [<span data-ttu-id="634bc-183">어셈블리를 사용한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="634bc-183">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="634bc-184">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="634bc-184">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="634bc-185">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="634bc-185">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="634bc-186">.NET Framework 앱 구성</span><span class="sxs-lookup"><span data-stu-id="634bc-186">Configuring .NET Framework Apps</span></span>](http://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)  
 [<span data-ttu-id="634bc-187">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="634bc-187">Runtime Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="634bc-188">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="634bc-188">Configuration File Schema</span></span>](../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="634bc-189">방법: 게시자 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="634bc-189">How to: Create a Publisher Policy</span></span>](../../../docs/framework/configure-apps/how-to-create-a-publisher-policy.md)
