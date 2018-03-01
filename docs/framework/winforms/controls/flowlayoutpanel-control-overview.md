---
title: "FlowLayoutPanel 컨트롤 개요"
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
- FlowLayoutPanel
helpviewer_keywords:
- forms [Windows Forms], dynamic layout
- layout [Windows Forms], dynamic
- Windows Forms, dynamic layout
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
ms.assetid: 3883e024-f5a0-456d-9c27-b4dfa1cc9045
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7eafe31bec86a969a12661c9f5629b2d55e3e3d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="flowlayoutpanel-control-overview"></a><span data-ttu-id="9d39f-102">FlowLayoutPanel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="9d39f-102">FlowLayoutPanel Control Overview</span></span>
<span data-ttu-id="9d39f-103"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤은 수평 또는 수직 방향으로 내용을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-103">The <xref:System.Windows.Forms.FlowLayoutPanel> control arranges its contents in a horizontal or vertical flow direction.</span></span> <span data-ttu-id="9d39f-104">컨트롤의 내용을 한 행에서 다음 행으로 또는 한 열에서 다음 열로 줄 바꿈할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-104">You can wrap the control's contents from one row to the next, or from one column to the next.</span></span> <span data-ttu-id="9d39f-105">또는 해당 내용을 줄 바꿈하는 대신 잘라낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-105">Alternately, you can clip instead of wrap its contents.</span></span>  
  
 <span data-ttu-id="9d39f-106"><xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> 속성의 값을 설정하여 흐름 방향을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-106">You can specify the flow direction by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> property.</span></span> <span data-ttu-id="9d39f-107"><xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤은 RTL(오른쪽에서 왼쪽) 레이아웃에서 흐름 방향을 올바르게 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-107">The <xref:System.Windows.Forms.FlowLayoutPanel> control correctly reverses its flow direction in Right-to-Left (RTL) layouts.</span></span> <span data-ttu-id="9d39f-108"><xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> 속성의 값을 설정하여 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 내용을 줄 바꿈할지 또는 잘라낼지 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-108">You can also specify whether the <xref:System.Windows.Forms.FlowLayoutPanel> control's contents are wrapped or clipped by setting the value of the <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A> property.</span></span>  
  
 <span data-ttu-id="9d39f-109"><xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 `true`로 설정하면 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤이 해당 내용에 맞게 자동으로 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-109">The <xref:System.Windows.Forms.FlowLayoutPanel> control automatically sizes to its contents when you set the <xref:System.Windows.Forms.Control.AutoSize%2A> property to `true`.</span></span> <span data-ttu-id="9d39f-110">또한 제공 된 **FlowBreak** 자식 컨트롤에 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-110">It also provides a **FlowBreak** property to its child controls.</span></span> <span data-ttu-id="9d39f-111">FlowBreak 속성의 값을 `true` 로 설정하면 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤이 현재 흐름 방향에서 컨트롤 레이아웃을 중지하고 다음 행이나 열로 줄 바꿈합니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-111">Setting the value of the FlowBreak property to `true` causes the <xref:System.Windows.Forms.FlowLayoutPanel> control to stop laying out controls in the current flow direction and wrap to the next row or column.</span></span>  
  
 <span data-ttu-id="9d39f-112">Windows Forms 컨트롤은 <xref:System.Windows.Forms.FlowLayoutPanel>의 다른 인스턴스를 포함하여 <xref:System.Windows.Forms.FlowLayoutPanel> 컨트롤의 자식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-112">Any Windows Forms control can be a child of the <xref:System.Windows.Forms.FlowLayoutPanel> control, including other instances of <xref:System.Windows.Forms.FlowLayoutPanel>.</span></span> <span data-ttu-id="9d39f-113">이 기능을 통해 런타임에 폼의 크기에 맞춰 조정되는 정교한 레이아웃을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-113">With this capability, you can construct sophisticated layouts that adapt to your form's dimensions at run time.</span></span>  
  
 <span data-ttu-id="9d39f-114">또한 참조 [연습: Windows Forms 사용 하 여 FlowLayoutPanel에서 컨트롤 정렬](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="9d39f-114">Also see [Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel](http://msdn.microsoft.com/library/z9w7ek2f\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d39f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d39f-115">See Also</span></span>  
 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 [<span data-ttu-id="9d39f-116">FlowLayoutPanel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9d39f-116">FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/flowlayoutpanel-control-windows-forms.md)
