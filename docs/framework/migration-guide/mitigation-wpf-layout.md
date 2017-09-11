---
title: "완화: WPF 레이아웃"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 805ffd7f-8d1e-427e-a648-601ca8ec37a5
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d3ba5ac792169cc076f9621025f35444281cec6e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-wpf-layout"></a><span data-ttu-id="5238f-102">완화: WPF 레이아웃</span><span class="sxs-lookup"><span data-stu-id="5238f-102">Mitigation: WPF Layout</span></span>
<span data-ttu-id="5238f-103">WPF 컨트롤의 레이아웃은 약간 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-103">The layout of WPF controls can change slightly.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="5238f-104">영향</span><span class="sxs-lookup"><span data-stu-id="5238f-104">Impact</span></span>  
 <span data-ttu-id="5238f-105">레이아웃을 변경한 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-105">As a result of this change:</span></span>  
  
-   <span data-ttu-id="5238f-106">요소의 너비나 높이가 최대 1픽셀씩 늘어나거나 줄어들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-106">The width or height of elements may grow or shrink by at most one pixel.</span></span>  
  
-   <span data-ttu-id="5238f-107">개체의 배치가 최대 1픽셀씩 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-107">The placement of an object can move by at most one pixel.</span></span>  
  
-   <span data-ttu-id="5238f-108">가운데 맞춤 요소가 가로 또는 세로로 최대 1픽셀씩 가운데에서 벗어날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-108">Centered elements can be vertically or horizontally off center by at most one pixel.</span></span>  
  
 <span data-ttu-id="5238f-109">기본적으로 이 새 레이아웃은 .NET Framework 4.6을 대상으로 하는 앱에 대해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-109">By default, this new layout is enabled only for apps that target the .NET Framework 4.6.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="5238f-110">완화</span><span class="sxs-lookup"><span data-stu-id="5238f-110">Mitigation</span></span>  
 <span data-ttu-id="5238f-111">이 수정은 높은 DPI에서 WPF 컨트롤의 오른쪽 또는 아래쪽의 클리핑을 제거하는 경향이 있으므로 이전 버전의 .NET Framework를 대상으로 하지만 NET Framework 4.6에서 실행되는 앱은 다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가하여 이 새 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-111">Since this modification tends to eliminate clipping of the right or bottom of WPF controls at high DPIs, apps that target earlier versions of the .NET Framework but are running on the .NET Framework 4.6 can opt into this new behavior by adding the following line to the `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=false" />  
```  
  
 <span data-ttu-id="5238f-112">.NET Framework 4.6을 대상으로 하지만 이전 레이아웃 알고리즘을 사용하여 WPF 컨트롤을 렌더링하려는 앱은 다음 줄을 app.config 파일의 `<runtime>` 섹션에 추가하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5238f-112">Apps that target the .NET Framework 4.6 but want WPF controls to render using the previous layout algorithm can do so by adding the following line to the  `<runtime>` section of the app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides value="Switch.MS.Internal.DoNotApplyLayoutRoundingToMarginsAndBorderThickness=true" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="5238f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5238f-113">See Also</span></span>  
 [<span data-ttu-id="5238f-114">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="5238f-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

