---
title: 공유 웹 호스팅을 위한 최적화
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3c979477f0928c9c3d2a393042867c84df33ecf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571971"
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="fcbb1-102">공유 웹 호스팅을 위한 최적화</span><span class="sxs-lookup"><span data-stu-id="fcbb1-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="fcbb1-103">여러 소규모 웹 사이트를 호스트하여 공유되는 서버의 관리자인 경우 .NET 디렉터리의 Aspnet.config 파일에서 `runtime` 노드에 ​​다음 `gcTrimCommitOnLowMemory` 설정을 추가하여 성능을 최적화하고 사이트 용량을 늘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="fcbb1-104">이 설정은 공유 웹 호스팅 시나리오에만 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="fcbb1-105">가비지 수집기가 향후 할당을 위해 메모리를 유지하므로 커밋된 공간이 엄밀히 필요한 것보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="fcbb1-106">시스템 메모리에 과부하가 발생할 때 충분한 공간을 제공하기 위해 이 공간을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="fcbb1-107">커밋된 이 공간을 줄이면 성능이 향상되고 용량이 확장되어 더 많은 사이트를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="fcbb1-108">`gcTrimCommitOnLowMemory` 설정을 사용하면 가비지 수집기가 시스템 메모리 로드를 평가하고 로드가 90%에 도달하는 경우 조정(trimming) 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="fcbb1-109">그리고 로드가 85% 미만으로 떨어질 때까지 조정 모드가 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="fcbb1-110">조건이 허용되는 경우 가비지 수집기는 `gcTrimCommitOnLowMemory` 설정으로 현재 응용 프로그램을 지원하지 않고 무시하도록 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcbb1-111">예</span><span class="sxs-lookup"><span data-stu-id="fcbb1-111">Example</span></span>  
 <span data-ttu-id="fcbb1-112">다음 XML 조각은 `gcTrimCommitOnLowMemory` 설정을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="fcbb1-113">줄임표는 `runtime` 노드에 있는 기타 설정을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fcbb1-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
```xml  
<?xml version="1.0" encoding="UTF-8"?>  
<configuration>  
    <runtime>  
    . . .  
    <gcTrimCommitOnLowMemory enabled="true"/>  
    </runtime>  
    . . .  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fcbb1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fcbb1-114">See Also</span></span>  
 [<span data-ttu-id="fcbb1-115">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="fcbb1-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
