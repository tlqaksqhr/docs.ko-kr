---
title: "TrackBar 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e62fc49a8a08c79138df080246b99b6fe891162e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="trackbar-control-overview-windows-forms"></a><span data-ttu-id="b3046-102">TrackBar 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b3046-102">TrackBar Control Overview (Windows Forms)</span></span>
<span data-ttu-id="b3046-103">Windows Forms <xref:System.Windows.Forms.TrackBar> 많은 양의 정보를 통해 탐색 또는 시각적으로 숫자 설정을 조정 하는 것에 대 한 제어도 ("slider" 컨트롤) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-103">The Windows Forms <xref:System.Windows.Forms.TrackBar> control (also sometimes called a "slider" control) is used for navigating through a large amount of information or for visually adjusting a numeric setting.</span></span> <span data-ttu-id="b3046-104"><xref:System.Windows.Forms.TrackBar> 컨트롤에는 두 부분이:는 엄지 단추 라고도 슬라이더의 눈금 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-104">The <xref:System.Windows.Forms.TrackBar> control has two parts: the thumb, also known as a slider, and the tick marks.</span></span> <span data-ttu-id="b3046-105">엄지 단추는 조정할 수 있는 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-105">The thumb is the part that can be adjusted.</span></span> <span data-ttu-id="b3046-106">엄지 단추의 위치는 <xref:System.Windows.Forms.TrackBar.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-106">Its position corresponds to the <xref:System.Windows.Forms.TrackBar.Value%2A> property.</span></span> <span data-ttu-id="b3046-107">눈금 표시 되는 일정 한 간격을 두고 배치 되어 시각적 표시기입니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-107">The tick marks are visual indicators that are spaced at regular intervals.</span></span> <span data-ttu-id="b3046-108">Trackbar에서 가로 또는 세로로 정렬 될을 지정 하는 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-108">The trackbar moves in increments that you specify and can be aligned horizontally or vertically.</span></span> <span data-ttu-id="b3046-109">예를 들어 시스템에 대 한 커서 깜박임 마우스 속도 제어 하려면 트랙 표시줄을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-109">For example, you might use the track bar to control the cursor blink rate or mouse speed for a system.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="b3046-110">키 속성</span><span class="sxs-lookup"><span data-stu-id="b3046-110">Key Properties</span></span>  
 <span data-ttu-id="b3046-111">키 속성은 <xref:System.Windows.Forms.TrackBar> 제어 <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, 및 <xref:System.Windows.Forms.TrackBar.Maximum%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-111">The key properties of the <xref:System.Windows.Forms.TrackBar> control are <xref:System.Windows.Forms.TrackBar.Value%2A>, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A>, <xref:System.Windows.Forms.TrackBar.Minimum%2A>, and <xref:System.Windows.Forms.TrackBar.Maximum%2A>.</span></span> <span data-ttu-id="b3046-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A>눈금 사이의 간격이입니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-112"><xref:System.Windows.Forms.TrackBar.TickFrequency%2A> is the spacing of the ticks.</span></span> <span data-ttu-id="b3046-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A>및 <xref:System.Windows.Forms.TrackBar.Maximum%2A> 트랙 표시줄에 나타낼 수 있는 최소 및 최대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-113"><xref:System.Windows.Forms.TrackBar.Minimum%2A> and <xref:System.Windows.Forms.TrackBar.Maximum%2A> are the smallest and largest values that can be represented on the track bar.</span></span>  
  
 <span data-ttu-id="b3046-114">다른 두 개의 중요 한 속성은 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 및 <xref:System.Windows.Forms.TrackBar.LargeChange%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-114">Two other important properties are <xref:System.Windows.Forms.TrackBar.SmallChange%2A> and <xref:System.Windows.Forms.TrackBar.LargeChange%2A>.</span></span> <span data-ttu-id="b3046-115">값은 <xref:System.Windows.Forms.TrackBar.SmallChange%2A> 속성은 위치가 엄지 단추를 왼쪽 또는 오른쪽 화살표 키를 누르면 지정 하는 응답 이동의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-115">The value of the <xref:System.Windows.Forms.TrackBar.SmallChange%2A> property is the number of positions the thumb moves in response to having the LEFT or RIGHT ARROW key pressed.</span></span> <span data-ttu-id="b3046-116">값은 <xref:System.Windows.Forms.TrackBar.LargeChange%2A> 속성은 엄지 단추를 지정 하는 PAGE UP 또는 PAGE DOWN 키를 누른 상태에 대 한 응답에서으로 이동 또는 조정 컨트롤의 어느 쪽에 트랙 표시줄 위에 클릭 마우스에 대 한 응답에서 위치의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3046-116">The value of the <xref:System.Windows.Forms.TrackBar.LargeChange%2A> property is the number of positions the thumb moves in response to having the PAGE UP or PAGE DOWN key pressed, or in response to mouse clicks on the track bar on either side of the thumb.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3046-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3046-117">See Also</span></span>  
 <xref:System.Windows.Forms.TrackBar>  
 [<span data-ttu-id="b3046-118">TrackBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="b3046-118">TrackBar Control</span></span>](../../../../docs/framework/winforms/controls/trackbar-control-windows-forms.md)
