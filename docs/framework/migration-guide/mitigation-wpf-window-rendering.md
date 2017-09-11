---
title: "완화: WPF 창 렌더링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 57d4cc56cc8d3a4dc3614043779eb09d7a8b8e25
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-wpf-window-rendering"></a><span data-ttu-id="16283-102">완화: WPF 창 렌더링</span><span class="sxs-lookup"><span data-stu-id="16283-102">Mitigation: WPF Window Rendering</span></span>
<span data-ttu-id="16283-103">Windows 8 이상에서 실행되는 [!INCLUDE[net_v46](../../../includes/net-v46-md.md)]에서, 다중 모니터 시나리오에서 전체 창이 단일 디스플레이를 벗어나 확장되는 경우 클리핑 없이 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="16283-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] running on Windows 8 and above, the entire window is rendered without clipping when it extends outside of single display in a multi-monitor scenario.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="16283-104">영향</span><span class="sxs-lookup"><span data-stu-id="16283-104">Impact</span></span>  
 <span data-ttu-id="16283-105">일반적으로 다중 모니터에서 클리핑 없이 전체 창이 렌더링되는 것은 예상된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="16283-105">In general, rendering an entire window across multiple monitors without clipping is the expected behavior.</span></span> <span data-ttu-id="16283-106">그러나 Windows 7 및 이전 버전에서 WPF 창이 단일 디스플레이를 벗어나 확장되면 두 번째 모니터 창의 일부를 렌더링할 때 성능에 큰 영향을 주기 때문에 WPF 창이 클리핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="16283-106">However, on Windows 7 and earlier versions, WPF windows are clipped when they extend beyond a single display because rendering a portion of the window on the second monitor has a significant performance impact.</span></span>  
  
 <span data-ttu-id="16283-107">Windows 8 이상에서 모니터 간의 WPF 창을 렌더링하는 작업에 미치는 영향은 수많은 요인에 따라 달라질 수 있으므로 정확하게 측정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16283-107">The precise impact of rendering WPF windows across monitors on Windows 8 and above is not precisely quantifiable since it depends on a large number of factors.</span></span> <span data-ttu-id="16283-108">경우에 따라서, 특히 그래픽 위주 응용 프로그램을 실행하고 여러 모니터에 걸친 창을 사용하는 경우 성능에 원하지 않는 영향이 계속 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16283-108">In some cases, it may still produce an undesirable impact on performance, particularly for users who run graphics-intensive applications and have windows straddling monitors.</span></span> <span data-ttu-id="16283-109">다른 경우에는 여러 .NET Framework 버전에서 일관된 동작이 발생하기를 원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16283-109">In other cases, you may simply want a consistent behavior across .NET Framework versions.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="16283-110">완화</span><span class="sxs-lookup"><span data-stu-id="16283-110">Mitigation</span></span>  
 <span data-ttu-id="16283-111">이 변경을 사용하지 않도록 설정하고 단일 디스플레이를 벗어나 확장될 때 WPF 창을 클리핑하는 이전 동작으로 되돌릴 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="16283-111">You can disable this change and revert to the previous behavior of clipping a WPF window when it extends beyond a single display.</span></span> <span data-ttu-id="16283-112">여기에는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16283-112">There are two ways to do this:</span></span>  
  
-   <span data-ttu-id="16283-113">응용 프로그램 구성 파일의 `<appSettings>` 섹션에 `<EnableMultiMonitorDisplayClipping>` 요소를 추가하여 Windows 8 이상에서 실행되는 앱에서 이 동작을 사용하지 않거나 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16283-113">By adding the `<EnableMultiMonitorDisplayClipping>` element to the `<appSettings>` section of your application configuration file, you can disable or enable this behavior on apps running on Windows 8 or later.</span></span> <span data-ttu-id="16283-114">예를 들어 다음 구성 섹션은 클리핑 없이 렌더링을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16283-114">For example, the following configuration section disables rendering without clipping:</span></span>  
  
    ```xml  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
    ```  
  
     <span data-ttu-id="16283-115">`<EnableMultiMonitorDisplayClipping>` 구성 설정에 다음 두 값 중 하나를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16283-115">The `<EnableMultiMonitorDisplayClipping>` configuration setting can have either of two values:</span></span>  
  
    -   <span data-ttu-id="16283-116">`true`, 렌더링하는 동안 창의 클리핑이 범위를 모니터링하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16283-116">`true`, to enable clipping of windows to monitor bounds during rendering.</span></span>  
  
    -   <span data-ttu-id="16283-117">`false`, 렌더링하는 동안 창의 클리핑이 범위를 모니터링하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16283-117">`false`, to disable clipping of windows to monitor bounds during rendering.</span></span>  
  
-   <span data-ttu-id="16283-118">앱을 시작할 때 <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="16283-118">By setting the <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> property to `true` at app startup.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16283-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16283-119">See Also</span></span>  
 [<span data-ttu-id="16283-120">런타임 변경 내용</span><span class="sxs-lookup"><span data-stu-id="16283-120">Runtime Changes</span></span>](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)

