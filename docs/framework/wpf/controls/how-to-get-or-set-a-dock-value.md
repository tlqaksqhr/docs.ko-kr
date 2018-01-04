---
title: "방법: Dock 값 가져오기 또는 설정"
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
helpviewer_keywords:
- Dock values [WPF], setting
- Dock values [WPF], getting
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7d663acf446ee2f7a36fc2d0c8605c31a0f2a84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-or-set-a-dock-value"></a><span data-ttu-id="af39b-102">방법: Dock 값 가져오기 또는 설정</span><span class="sxs-lookup"><span data-stu-id="af39b-102">How to: Get or Set a Dock Value</span></span>
<span data-ttu-id="af39b-103">다음 예제에서는 할당 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Dock> 개체에 대 한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="af39b-103">The following example shows how to assign a <xref:System.Windows.Controls.Dock> value for an object.</span></span> <span data-ttu-id="af39b-104">이 예제에서는 사용 된 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 및 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 의 메서드 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="af39b-104">The example uses the <xref:System.Windows.Controls.DockPanel.GetDock%2A> and <xref:System.Windows.Controls.DockPanel.SetDock%2A> methods of <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af39b-105">예</span><span class="sxs-lookup"><span data-stu-id="af39b-105">Example</span></span>  
 <span data-ttu-id="af39b-106">이 예에서는의 인스턴스를 만듭니다는 <xref:System.Windows.Controls.TextBlock> 요소를 `txt1`, 할당는 <xref:System.Windows.Controls.Dock> 값 `Top` 를 사용 하 여는 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드 <xref:System.Windows.Controls.DockPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="af39b-106">The example creates an instance of the <xref:System.Windows.Controls.TextBlock> element, `txt1`, and assigns a <xref:System.Windows.Controls.Dock> value of `Top` by using the <xref:System.Windows.Controls.DockPanel.SetDock%2A> method of <xref:System.Windows.Controls.DockPanel>.</span></span> <span data-ttu-id="af39b-107">값을 다음 추가 <xref:System.Windows.Controls.Dock> 속성을는 <xref:System.Windows.Controls.TextBlock.Text%2A> 의 <xref:System.Windows.Controls.TextBlock> 사용 하 여 요소는 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="af39b-107">It then appends the value of the <xref:System.Windows.Controls.Dock> property to the <xref:System.Windows.Controls.TextBlock.Text%2A> of the <xref:System.Windows.Controls.TextBlock> element by using the <xref:System.Windows.Controls.DockPanel.GetDock%2A> method.</span></span> <span data-ttu-id="af39b-108">마지막으로,이 예제에서는 추가 <xref:System.Windows.Controls.TextBlock> 부모 요소의 <xref:System.Windows.Controls.DockPanel>, `dp1`합니다.</span><span class="sxs-lookup"><span data-stu-id="af39b-108">Finally, the example adds the <xref:System.Windows.Controls.TextBlock> element to the parent <xref:System.Windows.Controls.DockPanel>, `dp1`.</span></span>  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="af39b-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af39b-109">See Also</span></span>  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [<span data-ttu-id="af39b-110">패널 개요</span><span class="sxs-lookup"><span data-stu-id="af39b-110">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
