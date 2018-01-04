---
title: "방법: DockPanel 요소를 사용하여 공간 분할"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [WPF], DockPanel
- DockPanel control [WPF], partitioning space
- partitioning space [WPF]
ms.assetid: a219b9e5-b205-4438-89b5-0a137ac463ab
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4adfabba76e9f6bf32e47fe4e52e42b68676bc0d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-partition-space-by-using-the-dockpanel-element"></a><span data-ttu-id="113c2-102">방법: DockPanel 요소를 사용하여 공간 분할</span><span class="sxs-lookup"><span data-stu-id="113c2-102">How to: Partition Space by Using the DockPanel Element</span></span>
<span data-ttu-id="113c2-103">다음 예제에서는 간단한 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 프레임 워크를 사용 하는 <xref:System.Windows.Controls.DockPanel> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-103">The following example creates a simple [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] framework using a <xref:System.Windows.Controls.DockPanel> element.</span></span> <span data-ttu-id="113c2-104"><xref:System.Windows.Controls.DockPanel> 자식 요소에 사용 가능한 공간을 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-104">The <xref:System.Windows.Controls.DockPanel> partitions available space to its child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="113c2-105">예</span><span class="sxs-lookup"><span data-stu-id="113c2-105">Example</span></span>  
 <span data-ttu-id="113c2-106">사용 하 여이 예제는 <xref:System.Windows.Controls.DockPanel.Dock%2A> 동일한 두 도킹 하려면 연결된 된 속성에 해당 하는 속성이 <xref:System.Windows.Controls.Border> 에 있는 요소는 <xref:System.Windows.Controls.Dock.Top> 분할 된 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-106">This example uses the <xref:System.Windows.Controls.DockPanel.Dock%2A> property, which is an attached property, to dock two identical <xref:System.Windows.Controls.Border> elements at the <xref:System.Windows.Controls.Dock.Top> of the partitioned space.</span></span> <span data-ttu-id="113c2-107">세 번째 <xref:System.Windows.Controls.Border> 요소를 도킹는 <xref:System.Windows.Controls.Dock.Left>, 200 픽셀으로 설정 하는 너비가 합니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-107">A third <xref:System.Windows.Controls.Border> element is docked to the <xref:System.Windows.Controls.Dock.Left>, with its width set to 200 pixels.</span></span> <span data-ttu-id="113c2-108">네 번째 <xref:System.Windows.Controls.Border> 에 도킹 된 <xref:System.Windows.Controls.Dock.Bottom> 화면입니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-108">A fourth <xref:System.Windows.Controls.Border> is docked to the <xref:System.Windows.Controls.Dock.Bottom> of the screen.</span></span> <span data-ttu-id="113c2-109">마지막 <xref:System.Windows.Controls.Border> 요소 나머지 공간을 자동으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-109">The last <xref:System.Windows.Controls.Border> element automatically fills the remaining space.</span></span>  
  
 [!code-cpp[DockPanelOvwSample#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/DockPanelOvwSample/CPP/DockPanel_Ovw_Sample.cpp#1)]
 [!code-csharp[DockPanelOvwSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelOvwSample/CSharp/DockPanel_Ovw_Sample.cs#1)]
 [!code-vb[DockPanelOvwSample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelOvwSample/VisualBasic/dockpanel_vb.vb#1)]
 [!code-xaml[DockPanelOvwSample#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DockPanelOvwSample/XAML/default.xaml#1)]  
  
> [!NOTE]
>  <span data-ttu-id="113c2-110">기본적으로 마지막 자식은 <xref:System.Windows.Controls.DockPanel> 요소 나머지 할당 되지 않은 공간을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-110">By default, the last child of a <xref:System.Windows.Controls.DockPanel> element fills the remaining unallocated space.</span></span> <span data-ttu-id="113c2-111">이 동작을 원하지 않으면 `LastChildFill="False"`을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-111">If you do not want this behavior, set `LastChildFill="False"`.</span></span>  
  
 <span data-ttu-id="113c2-112">컴파일된 응용 프로그램은 다음과 같은 새로운 UI를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="113c2-112">The compiled application yields a new UI that looks like this.</span></span>  
  
 <span data-ttu-id="113c2-113">![일반적인 DockPanel 시나리오](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span><span class="sxs-lookup"><span data-stu-id="113c2-113">![A typical DockPanel scenario.](../../../../docs/framework/wpf/controls/media/panel-intro-dockpanel.PNG "panel_intro_dockpanel")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113c2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="113c2-114">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 [<span data-ttu-id="113c2-115">패널 개요</span><span class="sxs-lookup"><span data-stu-id="113c2-115">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
