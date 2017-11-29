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
ms.openlocfilehash: 8ca4d7e753282a7c1d2236a70535e10d5109cd3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-or-set-a-dock-value"></a>방법: Dock 값 가져오기 또는 설정
다음 예제에서는 할당 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.Dock> 개체에 대 한 값입니다. 이 예제에서는 사용 된 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 및 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 의 메서드 <xref:System.Windows.Controls.DockPanel>합니다.  
  
## <a name="example"></a>예제  
 이 예에서는의 인스턴스를 만듭니다는 <xref:System.Windows.Controls.TextBlock> 요소를 `txt1`, 할당는 <xref:System.Windows.Controls.Dock> 값 `Top` 를 사용 하 여는 <xref:System.Windows.Controls.DockPanel.SetDock%2A> 메서드 <xref:System.Windows.Controls.DockPanel>합니다. 값을 다음 추가 <xref:System.Windows.Controls.Dock> 속성을는 <xref:System.Windows.Controls.TextBlock.Text%2A> 의 <xref:System.Windows.Controls.TextBlock> 사용 하 여 요소는 <xref:System.Windows.Controls.DockPanel.GetDock%2A> 메서드. 마지막으로,이 예제에서는 추가 <xref:System.Windows.Controls.TextBlock> 부모 요소의 <xref:System.Windows.Controls.DockPanel>, `dp1`합니다.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.DockPanel>  
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>  
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>  
 [패널 개요](../../../../docs/framework/wpf/controls/panels-overview.md)
