---
title: '완화: 경로 콜론 검사'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a54220a90a5120d13c89232d30ab40140c324097
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="042ac-102">완화: 경로 콜론 검사</span><span class="sxs-lookup"><span data-stu-id="042ac-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="042ac-103">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 이전에 지원되지 않던 경로를 지원하도록 여러 가지 변경이 수행되었습니다(길이 및 형식 측면에서).</span><span class="sxs-lookup"><span data-stu-id="042ac-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="042ac-104">특히 적절한 드라이브 구분 기호 구문(콜론)에 대한 확인이 좀 더 정확해졌습니다.</span><span class="sxs-lookup"><span data-stu-id="042ac-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="042ac-105">영향</span><span class="sxs-lookup"><span data-stu-id="042ac-105">Impact</span></span>  
 <span data-ttu-id="042ac-106">이러한 변경으로 인해 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> 메서드에서 이전에 지원했던 일부 URI 경로가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="042ac-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="042ac-107">완화</span><span class="sxs-lookup"><span data-stu-id="042ac-107">Mitigation</span></span>  
 <span data-ttu-id="042ac-108">전에는 허용되었지만 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> 메서드로 더 이상 지원되지 않는 경로 문제를 해결하려면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="042ac-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
-   <span data-ttu-id="042ac-109">URL에서 스키마를 수동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="042ac-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="042ac-110">예를 들어 URL에서 `file://`을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="042ac-110">For example, remove `file://` from a URL.</span></span>  
  
-   <span data-ttu-id="042ac-111">URI를 <xref:System.Uri> 생성자에 전달하고 <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> 속성 값을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="042ac-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
-   <span data-ttu-id="042ac-112">`Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> 스위치를 `true`로 설정하여 새 경로 정규화를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="042ac-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="042ac-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="042ac-113">See Also</span></span>  
 [<span data-ttu-id="042ac-114">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="042ac-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
