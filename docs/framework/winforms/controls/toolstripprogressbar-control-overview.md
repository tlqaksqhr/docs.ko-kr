---
title: ToolStripProgressBar 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- ToolStripProgressBar
helpviewer_keywords:
- toolbars [Windows Forms], progress bars
- progress controls [Windows Forms]
- ToolStripProgressBar control [Windows Forms], about ToolStripProgressBar control
ms.assetid: ec3ab522-5fe4-4b4d-a551-bc19e84f4774
ms.openlocfilehash: 0ce2347be055cc1840341747f202125cbbf678c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537754"
---
# <a name="toolstripprogressbar-control-overview"></a><span data-ttu-id="f8148-102">ToolStripProgressBar 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="f8148-102">ToolStripProgressBar Control Overview</span></span>
<span data-ttu-id="f8148-103"><xref:System.Windows.Forms.ToolStripProgressBar> 래프팅 (rafting) 및 모든 렌더링 기능이 결합 <xref:System.Windows.Forms.ToolStrip> 일반적인 프로세스 추적 기능을 사용 하 여 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-103">The <xref:System.Windows.Forms.ToolStripProgressBar> combines the rafting and rendering functionality of all <xref:System.Windows.Forms.ToolStrip> controls with its typical process-tracking functionality.</span></span> <span data-ttu-id="f8148-104">A <xref:System.Windows.Forms.ToolStripProgressBar> 에서 가장 일반적으로 호스트 <xref:System.Windows.Forms.StatusStrip>, 의해서도 자주는 <xref:System.Windows.Forms.ToolStrip>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-104">A <xref:System.Windows.Forms.ToolStripProgressBar> is most usually hosted by <xref:System.Windows.Forms.StatusStrip>, and less frequently by a <xref:System.Windows.Forms.ToolStrip>.</span></span>  
  
 <span data-ttu-id="f8148-105">하지만 <xref:System.Windows.Forms.ToolStripProgressBar> 대체 하 고 이전 버전에서 컨트롤에 기능을 추가 <xref:System.Windows.Forms.ToolStripProgressBar> 원하는 경우 이전 버전과 호환성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-105">Although <xref:System.Windows.Forms.ToolStripProgressBar> replaces and adds functionality to the control in previous versions, <xref:System.Windows.Forms.ToolStripProgressBar> is retained for both backward compatibility and future use if desired.</span></span>  
  
### <a name="important-toolstripprogressbar-members"></a><span data-ttu-id="f8148-106">중요 한 ToolStripProgressBar 멤버</span><span class="sxs-lookup"><span data-stu-id="f8148-106">Important ToolStripProgressBar Members</span></span>  
  
|<span data-ttu-id="f8148-107">이름</span><span class="sxs-lookup"><span data-stu-id="f8148-107">Name</span></span>|<span data-ttu-id="f8148-108">설명</span><span class="sxs-lookup"><span data-stu-id="f8148-108">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripProgressBar.MarqueeAnimationSpeed%2A>|<span data-ttu-id="f8148-109">각 간 지연 시간을 나타내는 값을 가져오거나 설정 합니다. <xref:System.Windows.Forms.ProgressBarStyle.Marquee> 밀리초 단위로 표시 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-109">Gets or sets a value representing the delay between each <xref:System.Windows.Forms.ProgressBarStyle.Marquee> display update, in milliseconds.</span></span>|  
|<xref:System.Windows.Forms.ProgressBar.Maximum%2A>|<span data-ttu-id="f8148-110">이 대해 정의 된 범위의 상한 값을 가져오거나 설정 합니다. <xref:System.Windows.Forms.ToolStripProgressBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-110">Gets or sets the upper bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Minimum%2A>|<span data-ttu-id="f8148-111">이 대해 정의 된 범위의 하한값을 가져오거나 설정 합니다. <xref:System.Windows.Forms.ToolStripProgressBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-111">Gets or sets the lower bound of the range that is defined for this <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Style%2A>|<span data-ttu-id="f8148-112">스타일을 가져오거나는 <xref:System.Windows.Forms.ToolStripProgressBar> 사용 하 여 작업의 진행률을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-112">Gets or sets the style that the <xref:System.Windows.Forms.ToolStripProgressBar> uses to display the progress of an operation.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.Value%2A>|<span data-ttu-id="f8148-113">현재 값을 가져오거나 설정 합니다.는 <xref:System.Windows.Forms.ToolStripProgressBar>합니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-113">Gets or sets the current value of the <xref:System.Windows.Forms.ToolStripProgressBar>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripProgressBar.PerformStep%2A>|<span data-ttu-id="f8148-114">진행률 표시줄의 현재 위치를 앞으로 이동의 양으로 <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f8148-114">Advances the current position of the progress bar by the amount of the <xref:System.Windows.Forms.ToolStripProgressBar.Step%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f8148-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8148-115">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripProgressBar>
