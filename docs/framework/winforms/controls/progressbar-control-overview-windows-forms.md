---
title: "ProgressBar 컨트롤 개요(Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ProgressBar
helpviewer_keywords:
- ProgressBar control [Windows Forms], about ProgressBar control
- progress controls [Windows Forms], about progress controls
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5ca5fd908124b0f38643c7b2833ba591be3b980
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-control-overview-windows-forms"></a><span data-ttu-id="bb45f-102">ProgressBar 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="bb45f-102">ProgressBar Control Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="bb45f-103"><xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-103">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="bb45f-104">Windows Forms <xref:System.Windows.Forms.ProgressBar> 컨트롤의 가로 막대에 정렬 된 사각형으로 적절 한 수를 표시 하 여 프로세스의 진행률을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-104">The Windows Forms <xref:System.Windows.Forms.ProgressBar> control indicates the progress of a process by displaying an appropriate number of rectangles arranged in a horizontal bar.</span></span> <span data-ttu-id="bb45f-105">프로세스가 완료 되 면 막대가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-105">When the process is complete, the bar is filled.</span></span> <span data-ttu-id="bb45f-106">진행률 표시줄 방법 이해할 사용자에 게 일반적으로 사용 되는 프로세스를 완료; 기다려야 하 예를 들어 때 큰 파일은 로드 중입니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-106">Progress bars are commonly used to give the user an idea of how long to wait for a process to complete; for instance, when a large file is being loaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb45f-107"><xref:System.Windows.Forms.ProgressBar> 컨트롤 수만 수 가로 방향으로 놓여 폼에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-107">The <xref:System.Windows.Forms.ProgressBar> control can only be oriented horizontally on the form.</span></span>  
  
## <a name="key-properties-and-methods"></a><span data-ttu-id="bb45f-108">키 속성 및 메서드</span><span class="sxs-lookup"><span data-stu-id="bb45f-108">Key Properties and Methods</span></span>  
 <span data-ttu-id="bb45f-109">키 속성은 <xref:System.Windows.Forms.ProgressBar> 제어 <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-109">The key properties of the <xref:System.Windows.Forms.ProgressBar> control are <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A>, and <xref:System.Windows.Forms.ProgressBar.Maximum%2A>.</span></span> <span data-ttu-id="bb45f-110"><xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성 진행률 표시줄에 표시 최대값과 최소값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-110">The <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties set the maximum and minimum values the progress bar can display.</span></span> <span data-ttu-id="bb45f-111"><xref:System.Windows.Forms.ProgressBar.Value%2A> 속성은 작업 이루어졌을 진행률을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-111">The <xref:System.Windows.Forms.ProgressBar.Value%2A> property represents the progress that has been made toward completing the operation.</span></span> <span data-ttu-id="bb45f-112">컨트롤에 표시 되는 표시줄 블록으로 구성 된 값으로 표시 된 <xref:System.Windows.Forms.ProgressBar> 제어 대략적는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 현재 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-112">Because the bar displayed in the control is composed of blocks, the value displayed by the <xref:System.Windows.Forms.ProgressBar> control only approximates the <xref:System.Windows.Forms.ProgressBar.Value%2A> property's current value.</span></span> <span data-ttu-id="bb45f-113">크기에 따라는 <xref:System.Windows.Forms.ProgressBar> 컨트롤의 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 다음 블록을 표시 하는 시기를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-113">Based on the size of the <xref:System.Windows.Forms.ProgressBar> control, the <xref:System.Windows.Forms.ProgressBar.Value%2A> property determines when to display the next block.</span></span>  
  
 <span data-ttu-id="bb45f-114">현재 진행률 값을 업데이트 하는 가장 일반적인 방법은 설정 하는 코드를 작성 하 여 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-114">The most common way to update the current progress value is to write code to set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="bb45f-115">큰 파일을 로드 하의 예제에서는 최대 (킬로바이트)에서 파일의 크기를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-115">In the example of loading a large file, you might set the maximum to the size of the file in kilobytes.</span></span> <span data-ttu-id="bb45f-116">예를 들어 경우는 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성이 100으로 설정 되어는 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 10, 속성 및 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성이 설정 되어 50 5 사각형이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-116">For example, if the <xref:System.Windows.Forms.ProgressBar.Maximum%2A> property is set to 100, the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> property is set to 10, and the <xref:System.Windows.Forms.ProgressBar.Value%2A> property is set to 50, 5 rectangles will be displayed.</span></span> <span data-ttu-id="bb45f-117">표시 될 수 있는 수의 절반입니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-117">This is half of the number that can be displayed.</span></span>  
  
 <span data-ttu-id="bb45f-118">그러나 표시 하는 값을 수정할 수 있는 방법이 있습니다.는 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 설정 하는 것 외의 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 직접 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-118">However, there are other ways to modify the value displayed by the <xref:System.Windows.Forms.ProgressBar> control, aside from setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property directly.</span></span> <span data-ttu-id="bb45f-119"><xref:System.Windows.Forms.ProgressBar.Step%2A> 증가 시킬 값을 지정 하려면 속성을 사용할 수는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-119">The <xref:System.Windows.Forms.ProgressBar.Step%2A> property can be used to specify a value to increment the <xref:System.Windows.Forms.ProgressBar.Value%2A> property by.</span></span> <span data-ttu-id="bb45f-120">그런 다음 호출에서 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 메서드 값이 증가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-120">Then, calling the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method will increment the value.</span></span> <span data-ttu-id="bb45f-121">증분 값을 변경 하는 데는 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 메서드 값을 지정 하 고는 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-121">To vary the increment value, you can use the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method and specify a value with which to increment the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span>  
  
 <span data-ttu-id="bb45f-122">그래픽으로 현재 작업에 대 한 사용자에 게 알려 주는 또 다른 컨트롤로 <xref:System.Windows.Forms.StatusBar> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-122">Another control that graphically informs the user about a current action is the <xref:System.Windows.Forms.StatusBar> control.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bb45f-123"><xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤 교체 및 기능을 추가 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나는 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 버전과 호환성 및 이후 사용에 대 한 컨트롤이 유지 되는 경우 있습니다 이 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb45f-123">The <xref:System.Windows.Forms.StatusStrip> and <xref:System.Windows.Forms.ToolStripStatusLabel> controls replace and add functionality to the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls; however, the <xref:System.Windows.Forms.StatusBar> and <xref:System.Windows.Forms.StatusBarPanel> controls are retained for both backward compatibility and future use, if you choose.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb45f-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb45f-124">See Also</span></span>  
 <xref:System.Windows.Forms.ProgressBar>  
 [<span data-ttu-id="bb45f-125">ProgressBar 컨트롤</span><span class="sxs-lookup"><span data-stu-id="bb45f-125">ProgressBar Control</span></span>](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)
