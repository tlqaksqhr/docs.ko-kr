---
title: "어셈블리 배치"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <codeBase> element
- locating assemblies
- assemblies [.NET Framework], placement
- assemblies [.NET Framework], location
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6669783cf6cac94e8b2335d4b475f1e2b6c5e7e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assembly-placement"></a><span data-ttu-id="895a6-102">어셈블리 배치</span><span class="sxs-lookup"><span data-stu-id="895a6-102">Assembly Placement</span></span>
<span data-ttu-id="895a6-103">대부분의 .NET Framework 응용 프로그램의 경우 해당 응용 프로그램을 구성하는 어셈블리는 응용 프로그램 디렉터리, 응용 프로그램 디렉터리의 하위 디렉터리 또는 전역 어셈블리 캐시(어셈블리가 공유된 경우)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895a6-103">For most .NET Framework applications, you locate assemblies that make up an application in the application's directory, in a subdirectory of the application's directory, or in the global assembly cache (if the assembly is shared).</span></span> <span data-ttu-id="895a6-104">구성 파일에 있는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하면 공용 언어 런타임에서 어셈블리를 검색하는 위치를 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895a6-104">You can override where the common language runtime looks for an assembly by using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) in a configuration file.</span></span> <span data-ttu-id="895a6-105">어셈블리에 강력한 이름이 없는 경우, [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 지정한 위치는 응용 프로그램 디렉터리와 그 하위 디렉터리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="895a6-105">If the assembly does not have a strong name, the location specified using the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) is restricted to the application directory or a subdirectory.</span></span> <span data-ttu-id="895a6-106">반면, 강력한 이름의 어셈블리인 경우에는 [\<codeBase> 요소](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)를 사용하여 컴퓨터 또는 네트워크상의 모든 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895a6-106">If the assembly has a strong name, the [\<codeBase> Element](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) can specify any location on the computer or on a network.</span></span>  
  
 <span data-ttu-id="895a6-107">비관리 코드나 COM interop 응용 프로그램에 대해 어셈블리의 위치를 검색할 때도 이와 비슷한 규칙이 적용됩니다. 여러 응용 프로그램에서 해당 어셈블리를 공유해야 하는 경우에는 어셈블리는 전역 어셈블리 캐시에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895a6-107">Similar rules apply to locating assemblies when working with unmanaged code or COM interop applications: if the assembly will be shared by multiple applications, it should be installed into the global assembly cache.</span></span> <span data-ttu-id="895a6-108">비관리 코드에 사용되는 어셈블리는 형식 라이브러리로 내보낸 후 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895a6-108">Assemblies used with unmanaged code must be exported as a type library and registered.</span></span> <span data-ttu-id="895a6-109">COM interop에 사용되는 어셈블리는 카달로그에 등록해야 하는데, 경우에 따라서는 어셈블리가 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="895a6-109">Assemblies used by COM interop must be registered in the catalog, although in some cases this registration occurs automatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="895a6-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="895a6-110">See Also</span></span>  
 [<span data-ttu-id="895a6-111">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="895a6-111">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="895a6-112">응용 프로그램 구성</span><span class="sxs-lookup"><span data-stu-id="895a6-112">Configuring Apps</span></span>](../../../docs/framework/configure-apps/index.md)  
 [<span data-ttu-id="895a6-113">고급 COM 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="895a6-113">Advanced COM Interoperability</span></span>](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 [<span data-ttu-id="895a6-114">공용 언어 런타임의 어셈블리</span><span class="sxs-lookup"><span data-stu-id="895a6-114">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
