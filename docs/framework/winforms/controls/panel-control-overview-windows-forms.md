---
title: "Panel 컨트롤 개요(Windows Forms)"
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
- Panel
helpviewer_keywords:
- grouping controls [Windows Forms], Panel control
- Panel control [Windows Forms], about Panel control
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8855c88a0ec60cd0d44d73046e44c9614347d90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="panel-control-overview-windows-forms"></a><span data-ttu-id="c0fdb-102">Panel 컨트롤 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c0fdb-102">Panel Control Overview (Windows Forms)</span></span>
<span data-ttu-id="c0fdb-103">Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤에 대 한 식별 가능한 그룹화를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-103">Windows Forms <xref:System.Windows.Forms.Panel> controls are used to provide an identifiable grouping for other controls.</span></span> <span data-ttu-id="c0fdb-104">일반적으로 폼 함수로 세분화 하 패널을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-104">Typically, you use panels to subdivide a form by function.</span></span> <span data-ttu-id="c0fdb-105">예를 들어 어떤 야간 운송 같은 메일링 옵션을 지정 하는 주문 양식과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-105">For example, you may have an order form that specifies mailing options such as which overnight carrier to use.</span></span> <span data-ttu-id="c0fdb-106">패널에 있는 모든 옵션을 그룹화 하면 오류가 논리 시각적 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-106">Grouping all options in a panel gives the user a logical visual cue.</span></span> <span data-ttu-id="c0fdb-107">디자인 타임에 컨트롤을 쉽게 이동할 수 있습니다. 모든-이동 하는 경우는 <xref:System.Windows.Forms.Panel> 모든 포함 된 컨트롤이, 너무 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-107">At design time all the controls can be moved easily — when you move the <xref:System.Windows.Forms.Panel> control, all its contained controls move, too.</span></span> <span data-ttu-id="c0fdb-108">패널에 그룹화 된 컨트롤을 통해 액세스할 수는 <xref:System.Windows.Forms.Control.Controls%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-108">The controls grouped in a panel can be accessed through its <xref:System.Windows.Forms.Control.Controls%2A> property.</span></span> <span data-ttu-id="c0fdb-109">이 속성의 컬렉션을 반환 <xref:System.Windows.Forms.Control> 되므로 컨트롤을 캐스팅 해야 일반적으로 인스턴스를 특정 형식으로 이러한 방식으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-109">This property returns a collection of <xref:System.Windows.Forms.Control> instances, so you will typically need to cast a control retrieved this way to its specific type.</span></span>  
  
## <a name="panel-versus-groupbox"></a><span data-ttu-id="c0fdb-110">GroupBox와 패널</span><span class="sxs-lookup"><span data-stu-id="c0fdb-110">Panel Versus GroupBox</span></span>  
 <span data-ttu-id="c0fdb-111"><xref:System.Windows.Forms.Panel> 제어는 비슷합니다는 <xref:System.Windows.Forms.GroupBox> 제어; 그러나만 <xref:System.Windows.Forms.Panel> 컨트롤에서 스크롤 막대를 가질 수 있습니다 및만 해당는 <xref:System.Windows.Forms.GroupBox> 컨트롤 캡션을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-111">The <xref:System.Windows.Forms.Panel> control is similar to the <xref:System.Windows.Forms.GroupBox> control; however, only the <xref:System.Windows.Forms.Panel> control can have scroll bars, and only the <xref:System.Windows.Forms.GroupBox> control displays a caption.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="c0fdb-112">키 속성</span><span class="sxs-lookup"><span data-stu-id="c0fdb-112">Key Properties</span></span>  
 <span data-ttu-id="c0fdb-113">스크롤 막대를 표시 하려면 설정는 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-113">To display scroll bars, set the <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> property to `true`.</span></span> <span data-ttu-id="c0fdb-114">설정 하 여 패널의 모양을 사용자 지정할 수도 있습니다는 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, 및 <xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-114">You can also customize the appearance of the panel by setting the <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A>, and <xref:System.Windows.Forms.Panel.BorderStyle%2A> properties.</span></span> <span data-ttu-id="c0fdb-115">대 한 자세한 내용은 <xref:System.Windows.Forms.Control.BackColor%2A> 및 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성 참조 [하는 방법: 패널의 배경 설정](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c0fdb-115">For more information on the <xref:System.Windows.Forms.Control.BackColor%2A> and <xref:System.Windows.Forms.Control.BackgroundImage%2A> properties, see [How to: Set the Background of a Panel](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md).</span></span> <span data-ttu-id="c0fdb-116"><xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성 패널 테두리가 표시 되지으로 작성 된 경우를 결정 (<xref:System.Windows.Forms.BorderStyle.None>), 일반 줄 (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), 또는 음영된 선 (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).</span><span class="sxs-lookup"><span data-stu-id="c0fdb-116">The <xref:System.Windows.Forms.Panel.BorderStyle%2A> property determines if the panel is outlined with no visible border (<xref:System.Windows.Forms.BorderStyle.None>), a plain line (<xref:System.Windows.Forms.BorderStyle.FixedSingle>), or a shadowed line (<xref:System.Windows.Forms.BorderStyle.Fixed3D>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0fdb-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c0fdb-117">See Also</span></span>  
 <xref:System.Windows.Forms.Panel>  
 [<span data-ttu-id="c0fdb-118">GroupBox 컨트롤</span><span class="sxs-lookup"><span data-stu-id="c0fdb-118">GroupBox Control</span></span>](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)  
 [<span data-ttu-id="c0fdb-119">방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화</span><span class="sxs-lookup"><span data-stu-id="c0fdb-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)  
 [<span data-ttu-id="c0fdb-120">방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정</span><span class="sxs-lookup"><span data-stu-id="c0fdb-120">How to: Set the Background of a Windows Forms Panel Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)
