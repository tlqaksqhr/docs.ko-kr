---
title: "ToolTip 구성 요소 개요(Windows Forms)"
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
- ToolTip
helpviewer_keywords:
- tooltips [Windows Forms], about tooltips
- ToolTip component [Windows Forms], about ToolTip component
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fce1cb5750197e52461b4883f1238325fa10fc5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="tooltip-component-overview-windows-forms"></a><span data-ttu-id="63f53-102">ToolTip 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="63f53-102">ToolTip Component Overview (Windows Forms)</span></span>
<span data-ttu-id="63f53-103">Windows Forms <xref:System.Windows.Forms.ToolTip> 구성 요소는 사용자가 컨트롤을 가리킬 때 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-103">The Windows Forms <xref:System.Windows.Forms.ToolTip> component displays text when the user points at controls.</span></span> <span data-ttu-id="63f53-104">도구 설명은 모든 컨트롤에 연결될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-104">A ToolTip can be associated with any control.</span></span> <span data-ttu-id="63f53-105">이 구성 요소의 사용 예: 폼에 공간을 절약 하려면 단추에 작은 아이콘을 표시 하 수 단추의 기능을 설명 하는 도구 설명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-105">An example use of this component: to save space on a form, you can display a small icon on a button and use a ToolTip to explain the button's function.</span></span>  
  
## <a name="working-with-the-tooltip-component"></a><span data-ttu-id="63f53-106">ToolTip 구성 요소 사용</span><span class="sxs-lookup"><span data-stu-id="63f53-106">Working with the ToolTip Component</span></span>  
 <span data-ttu-id="63f53-107">A <xref:System.Windows.Forms.ToolTip> 구성 요소를 제공는 `ToolTip` Windows Form 또는 다른 컨테이너에 여러 컨트롤에는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-107">A <xref:System.Windows.Forms.ToolTip> component provides a `ToolTip` property to multiple controls on a Windows Form or other container.</span></span> <span data-ttu-id="63f53-108">예를 들어 하나를 저장 하는 경우 <xref:System.Windows.Forms.ToolTip> 폼에 구성 요소에 대 한 "여기에 이름을 입력"를 표시할 수 있습니다는 <xref:System.Windows.Forms.TextBox> 제어 하 고 "여기를 클릭 ब ा ळ"에 대 한는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-108">For example, if you place one <xref:System.Windows.Forms.ToolTip> component on a form, you can display "Type your name here" for a <xref:System.Windows.Forms.TextBox> control and "Click here to save changes" for a <xref:System.Windows.Forms.Button> control.</span></span>  
  
 <span data-ttu-id="63f53-109">주요 메서드는 <xref:System.Windows.Forms.ToolTip> 구성 요소는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 및 <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-109">The key methods of the <xref:System.Windows.Forms.ToolTip> component are <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> and <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.</span></span> <span data-ttu-id="63f53-110">사용할 수는 <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> 메서드를 컨트롤에 표시할 도구 설명을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-110">You can use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method to set the ToolTips displayed for controls.</span></span> <span data-ttu-id="63f53-111">자세한 내용은 참조 [하는 방법: 디자인 타임에 Windows Form의 컨트롤에 대 한 도구 설명을 설정](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-111">For more information, see [How to: Set ToolTips for Controls on a Windows Form at Design Time](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).</span></span> <span data-ttu-id="63f53-112">주요 속성은 <xref:System.Windows.Forms.ToolTip.Active%2A>로 설정 해야 `true` 나타날 도구 설명에 대 한 및 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, 도구 설명 문자열이 표시 되는 시간의 길이 설정 하는, 사용자 표시 도구 설명 컨트롤에서 가리켜야 기간 및 긴 것 방법 다음 도구 설명 창이 나타날을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-112">The key properties are <xref:System.Windows.Forms.ToolTip.Active%2A>, which must be set to `true` for the ToolTip to appear, and <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, which sets the length of time that the ToolTip string is shown, how long the user must point at the control for the ToolTip to appear, and how long it takes for subsequent ToolTip windows to appear.</span></span> <span data-ttu-id="63f53-113">자세한 내용은 참조 [하는 방법: Windows Forms ToolTip 구성 요소의 지연 변경](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="63f53-113">For more information, see [How to: Change the Delay of the Windows Forms ToolTip Component](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63f53-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63f53-114">See Also</span></span>  
 <xref:System.Windows.Forms.ToolTip>  
 [<span data-ttu-id="63f53-115">방법: 디자인 타임에 Windows Form의 컨트롤에 도구 설명 설정</span><span class="sxs-lookup"><span data-stu-id="63f53-115">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [<span data-ttu-id="63f53-116">방법: Windows Forms ToolTip 구성 요소의 지연 변경</span><span class="sxs-lookup"><span data-stu-id="63f53-116">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
