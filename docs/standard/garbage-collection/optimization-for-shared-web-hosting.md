---
title: "공유 웹 호스팅을 위한 최적화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- garbage collection, Web hosting
- garbage collection, optimizing
- garbage collection, shared Web hosting
ms.assetid: be98c0ab-7ef8-409f-8a0d-cb6e5b75ff20
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1f423d867d4fada075800650627c94f9d09e9e7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="optimization-for-shared-web-hosting"></a><span data-ttu-id="e6318-102">공유 웹 호스팅을 위한 최적화</span><span class="sxs-lookup"><span data-stu-id="e6318-102">Optimization for Shared Web Hosting</span></span>
<span data-ttu-id="e6318-103">여러 개의 작은 웹 사이트를 호스트 하 여 공유 하는 서버에 대 한 관리자 인 경우 성능을 최적화 하 고 다음을 추가 하 여 사이트 용량을 늘릴 수 `gcTrimCommitOnLowMemory` 을로 설정 된 `runtime` .NET에 Aspnet.config 파일에 있는 노드 디렉터리:</span><span class="sxs-lookup"><span data-stu-id="e6318-103">If you are the administrator for a server that is shared by hosting several small Web sites, you can optimize performance and increase site capacity by adding the following `gcTrimCommitOnLowMemory` setting to the `runtime` node in the Aspnet.config file in the .NET directory:</span></span>  
  
 `<gcTrimCommitOnLowMemory enabled="true|false"/>`  
  
> [!NOTE]
>  <span data-ttu-id="e6318-104">이 설정은 호스팅 시나리오 공유 웹에만 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-104">This setting is recommended only for shared Web hosting scenarios.</span></span>  
  
 <span data-ttu-id="e6318-105">가비지 수집기는 이후 할당에 대 한 메모리를 보존, 때문에 커밋된 공간이 꼭 필요한 것 보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-105">Because the garbage collector retains memory for future allocations, its committed space can be more than what is strictly needed.</span></span> <span data-ttu-id="e6318-106">이 공간 시간을 줄일 수 있으면 시스템 메모리에 상당한 부하를 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-106">You can reduce this space to accommodate times when there is a heavy load on system memory.</span></span> <span data-ttu-id="e6318-107">이 커밋된 공간 줄이기 성능이 향상 됩니다 하 고 더 많은 사이트를 호스트 하는 기능을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-107">Reducing this committed space improves performance and expands the capacity to host more sites.</span></span>  
  
 <span data-ttu-id="e6318-108">경우는 `gcTrimCommitOnLowMemory` 설정을 사용 하는, 가비지 수집기 시스템 메모리 로드를 평가 하 고 부하 90%에 도달할 때 트리밍 모드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-108">When the `gcTrimCommitOnLowMemory` setting is enabled, the garbage collector evaluates the system memory load and enters a trimming mode when the load reaches 90%.</span></span> <span data-ttu-id="e6318-109">부하 85% 미만 떨어져야 트리밍 모드를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-109">It maintains the trimming mode until the load drops under 85%.</span></span>  
  
 <span data-ttu-id="e6318-110">가비지 수집기를 결정할 수 조건이 충족 될 경우는 `gcTrimCommitOnLowMemory` 설정을 현재 응용 프로그램에 도움이 되지 않습니다 되며 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-110">When conditions permit, the garbage collector can decide that the `gcTrimCommitOnLowMemory` setting will not help the current application and ignore it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6318-111">예제</span><span class="sxs-lookup"><span data-stu-id="e6318-111">Example</span></span>  
 <span data-ttu-id="e6318-112">다음 XML 조각은 방법을 볼 수는 `gcTrimCommitOnLowMemory` 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6318-112">The following XML fragment shows how to enable the `gcTrimCommitOnLowMemory` setting.</span></span> <span data-ttu-id="e6318-113">타원에 있을 수 있는 다른 설정을 나타내는 `runtime` 노드.</span><span class="sxs-lookup"><span data-stu-id="e6318-113">Ellipses indicate other settings that would be in the `runtime` node.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e6318-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6318-114">See Also</span></span>  
 [<span data-ttu-id="e6318-115">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="e6318-115">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
