---
title: Windows Forms 컨트롤의 레이아웃
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windws Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: 11db7b49f37b4367f31b2c27c61225f8f71bde80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535843"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="5bfd4-102">Windows Forms 컨트롤의 레이아웃</span><span class="sxs-lookup"><span data-stu-id="5bfd4-102">Layout in Windows Forms Controls</span></span>
<span data-ttu-id="5bfd4-103">폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="5bfd4-104"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임 스페이스는 여러 레이아웃 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5bfd4-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="5bfd4-105">In This Section</span></span>  
 [<span data-ttu-id="5bfd4-106">AutoSize 속성 개요</span><span class="sxs-lookup"><span data-stu-id="5bfd4-106">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 <span data-ttu-id="5bfd4-107">설명의 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성 및 레이아웃에서의 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>  
  
 [<span data-ttu-id="5bfd4-108">Windows Forms 컨트롤의 여백 및 안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="5bfd4-108">Margin and Padding in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)  
 <span data-ttu-id="5bfd4-109">설명의 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 속성 및 레이아웃에서의 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>  
  
 [<span data-ttu-id="5bfd4-110">방법: 컨트롤을 폼의 가장자리에 맞춤</span><span class="sxs-lookup"><span data-stu-id="5bfd4-110">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 <span data-ttu-id="5bfd4-111">사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 사용자 컨트롤을 폼의 가장자리를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="5bfd4-112">방법: 안쪽 여백을 사용하여 Windows Forms 컨트롤 주위에 테두리 만들기</span><span class="sxs-lookup"><span data-stu-id="5bfd4-112">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)  
 <span data-ttu-id="5bfd4-113">사용 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 컨트롤에 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>  
  
 [<span data-ttu-id="5bfd4-114">방법: 사용자 지정 레이아웃 엔진 구현</span><span class="sxs-lookup"><span data-stu-id="5bfd4-114">How to: Implement a Custom Layout Engine</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)  
 <span data-ttu-id="5bfd4-115">구현 하는 방법을 보여 줍니다.는 <xref:System.Windows.Forms.Layout.LayoutEngine> 을 Windows Forms 컨트롤을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5bfd4-116">참조</span><span class="sxs-lookup"><span data-stu-id="5bfd4-116">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="5bfd4-117"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="5bfd4-118"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5bfd4-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bfd4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bfd4-119">See Also</span></span>  
 [<span data-ttu-id="5bfd4-120">방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="5bfd4-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="5bfd4-121">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="5bfd4-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="5bfd4-122">방법: 지역화에 적합한 Windows Forms 레이아웃 디자인</span><span class="sxs-lookup"><span data-stu-id="5bfd4-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="5bfd4-123">TableLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="5bfd4-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)
