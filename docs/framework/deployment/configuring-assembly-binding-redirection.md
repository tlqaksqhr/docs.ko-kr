---
title: 어셈블리 바인딩 리디렉션 구성
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution, assembly binding redirection
- assemblies [.NET Framework], binding redirection
ms.assetid: d266cbd8-bf91-41d1-baf0-afbc481a741f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04743dc7a0fc821f2e3b94929e2384eb25c69f2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33387187"
---
# <a name="configuring-assembly-binding-redirection"></a><span data-ttu-id="70606-102">어셈블리 바인딩 리디렉션 구성</span><span class="sxs-lookup"><span data-stu-id="70606-102">Configuring Assembly Binding Redirection</span></span>
<span data-ttu-id="70606-103">기본적으로 응용 프로그램에서는 응용 프로그램을 컴파일하는 데 사용된 런타임 버전과 함께 제공된 .NET Framework 어셈블리 집합을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-103">By default, applications use the set of .NET Framework assemblies that shipped with the runtime version used to compile the application.</span></span> <span data-ttu-id="70606-104">응용 프로그램 구성 파일에서 [\<assemblyBinding>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) 요소에 대해 **appliesTo** 특성을 사용하여 어셈블리 바인딩 참조를 .NET Framework 어셈블리의 특정 버전으로 리디렉션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70606-104">You can use the **appliesTo** attribute on the [\<assemblyBinding>](../../../docs/framework/configure-apps/file-schema/runtime/assemblybinding-element-for-runtime.md) element in an application configuration file to redirect assembly binding references to a specific version of the .NET Framework assemblies.</span></span> <span data-ttu-id="70606-105">이 선택적 특성은 .NET Framework 버전을 사용하여 특성이 적용되는 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-105">This optional attribute uses a .NET Framework version number to indicate which version it applies to.</span></span> <span data-ttu-id="70606-106">**appliesTo** 특성이 지정되지 않으면 **\<assemblyBinding>** 요소는 .NET Framework의 모든 버전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70606-106">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="70606-107">**appliesTo** 특성은 .NET Framework 버전 1.1에서 도입되었고 .NET Framework 버전 1.0에서는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70606-107">The **appliesTo** attribute was introduced in the .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="70606-108">즉, .NET Framework 버전 1.0을 사용할 때는 **appliesTo** 특성을 지정해도 모든 **\<assemblyBinding>** 요소가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70606-108">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70606-109">**appliesTo** 특성을 사용하여 특정 런타임 버전으로 리디렉션되는 어셈블리 바인딩을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-109">Use the **appliesTo** attribute to limit assembly binding redirection to a specific version of the runtime.</span></span>  
  
 <span data-ttu-id="70606-110">예를 들어 .NET Framework 버전 1.0 어셈블리에 대한 어셈블리 바인딩을 리디렉션하려면 응용 프로그램 구성 파일에 다음 XML 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-110">For example, to redirect assembly binding for a .NET Framework version 1.0 assembly, you would include the following XML code in your application configuration file.</span></span>  
  
```xml  
<runtime>  
        <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
            <dependentAssembly>   
               * assembly information goes here *  
            </dependentAssembly>  
       </assemblyBinding>  
</runtime>  
```  
  
 <span data-ttu-id="70606-111">**\<assemblyBinding>** 요소는 순서를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-111">The **\<assemblyBinding>** elements are order-sensitive.</span></span> <span data-ttu-id="70606-112">먼저 .NET Framework 버전 1.0 어셈블리에 대한 어셈블리 바인딩 리디렉션 정보를 입력하고 .NET Framework 버전 1.1 어셈블리에 대한 어셈블리 바인딩 리디렉션 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-112">You should enter assembly binding redirection information for any .NET Framework version 1.0 assemblies first, followed by assembly binding redirection information for any .NET Framework version 1.1 assemblies.</span></span> <span data-ttu-id="70606-113">마지막으로 **appliesTo** 특성을 사용하지 않으므로 모든 .NET Framework 버전에 적용되는 .NET Framework 어셈블리 리디렉션에 대한 어셈블리 바인딩 리디렉션 정보를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-113">Finally, enter assembly binding redirection information for any .NET Framework assembly redirection that does not use the **appliesTo** attribute and therefore applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="70606-114">리디렉션 시 충돌이 발생하면 구성 파일에서 일치하는 첫 번째 리디렉션 문이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="70606-114">In case of a conflict in redirection, the first matching redirection statement in the configuration file is used.</span></span>  
  
 <span data-ttu-id="70606-115">예를 들어 한 참조를 .NET Framework 버전 1.0 어셈블리로 리디렉션하고 다른 참조를 .NET Framework 버전 1.1 어셈블리로 리디렉션하려면 다음 의사 코드에 표시된 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-115">For example, to redirect one reference to a .NET Framework version 1.0 assembly and another reference to a .NET Framework version 1.1 assembly, you would use the pattern shown in the following pseudocode.</span></span>  
  
```xml  
<assemblyBinding xmlns="..." appliesTo="v1.0.3705">   
<! — .NET Framework version 1.0 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="..." appliesTo="v1.1.4322">   
    <! — .NET Framework version 1.1 redirects here. -->   
</assemblyBinding>   
  
<assemblyBinding xmlns="...">   
<!-- Redirects meant for all versions of the .NET Framework. -->   
</assemblyBinding>  
```  
  
## <a name="debugging-configuration-file-errors"></a><span data-ttu-id="70606-116">구성 파일 오류 디버깅</span><span class="sxs-lookup"><span data-stu-id="70606-116">Debugging Configuration File Errors</span></span>  
 <span data-ttu-id="70606-117">런타임에서는 응용 프로그램이 만들어질 때 구성 파일을 한 번 구문 분석하고 코드를 해당 응용 프로그램 도메인으로 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-117">The runtime parses configuration files once when an application domain is created, and loads code into that application domain.</span></span> <span data-ttu-id="70606-118">공용 언어 런타임에서는 입력을 무시하는 방식으로 구성 파일의 오류를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-118">The common language runtime handles errors in a configuration file by ignoring the entry.</span></span> <span data-ttu-id="70606-119">형식이 잘못된 XML이 포함된 런타임에서는 전체 구성 파일을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-119">The runtime ignores the entire configuration file if it contains malformed XML.</span></span> <span data-ttu-id="70606-120">잘못된 XML의 경우 잘못된 섹션만 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="70606-120">For invalid XML, only the invalid sections are ignored.</span></span>  
  
 <span data-ttu-id="70606-121">어셈블리 바인딩이 리디렉션이 발생하는지를 확인하여 구성 파일이 사용되고 있는지를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70606-121">You can determine whether a configuration file is being used by determining whether assembly binding redirects are occurring.</span></span> <span data-ttu-id="70606-122">[어셈블리 바인딩 로그 뷰어(Fuslogvw.exe)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md)를 사용하여 로드되고 있는 어셈블리를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-122">Use the [Assembly Binding Log Viewer (Fuslogvw.exe)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md) to see which assemblies are being loaded.</span></span> <span data-ttu-id="70606-123">모든 어셈블리 바인드를 확인하려면 레지스트리에서 **ForceLog**에 대한 항목을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70606-123">To see all assembly binds, you must set an entry for **ForceLog** in the registry.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70606-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70606-124">See Also</span></span>  
 [<span data-ttu-id="70606-125">방법: 자동 바인딩 리디렉션 사용 설정 및 해제</span><span class="sxs-lookup"><span data-stu-id="70606-125">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)
