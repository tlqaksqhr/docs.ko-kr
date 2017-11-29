---
title: "Windows Forms 컨트롤의 여백 및 안쪽 여백"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22d8a73963a8f9f1e3d8b80b6c16f189e0221c55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="047c5-102">Windows Forms 컨트롤의 여백 및 안쪽 여백</span><span class="sxs-lookup"><span data-stu-id="047c5-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="047c5-103">폼의 정확한 컨트롤 배치는 많은 응용 프로그램에서 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="047c5-104"><xref:System.Windows.Forms?displayProperty=nameWithType> 네임스페이스는 이 목적을 위한 다양한 레이아웃 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="047c5-105">가장 중요한 두 가지 기능은 <xref:System.Windows.Forms.Control.Margin%2A> 및 <xref:System.Windows.Forms.Control.Padding%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="047c5-106"><xref:System.Windows.Forms.Control.Margin%2A> 속성은 다른 컨트롤을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 주위의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="047c5-107"><xref:System.Windows.Forms.Control.Padding%2A> 속성은 컨트롤의 내용(예: <xref:System.Windows.Forms.Control.Text%2A> 속성의 값)을 컨트롤의 테두리에서 지정된 거리에 유지하는 컨트롤 내부의 공간을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="047c5-108">다음 그림에서는 컨트롤의 <xref:System.Windows.Forms.Control.Padding%2A> 및 <xref:System.Windows.Forms.Control.Margin%2A> 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="047c5-109">![안쪽 여백 및 여백을 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="047c5-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="047c5-110">Visual Studio에서는 디자인 타임에 이 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-110">There is design-time support for this feature in Visual Studio.</span></span>  <span data-ttu-id="047c5-111">또한 참조 [연습: 레이아웃으로 Windows Forms 컨트롤 Padding, Margins 및 AutoSize 속성](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="047c5-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="047c5-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="047c5-112">See Also</span></span>  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 <xref:System.Windows.Forms.Control.LayoutEngine%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
