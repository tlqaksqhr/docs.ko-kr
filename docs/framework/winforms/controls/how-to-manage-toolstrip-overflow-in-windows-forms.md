---
title: "방법: Windows Forms의 ToolStrip 오버플로 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 619c4832626693a56280c70af3ade5dbb9e9d4de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>방법: Windows Forms의 ToolStrip 오버플로 관리
경우에 있는 모든 항목이 <xref:System.Windows.Forms.ToolStrip> 제어 할당된 된 공간에 맞지 않는에서 오버플로 기능을 사용할 수 있습니다는 <xref:System.Windows.Forms.ToolStrip> 특정 오버플로 동작을 결정 하 고 <xref:System.Windows.Forms.ToolStripItem>s입니다.  
  
 추가 하는 경우 <xref:System.Windows.Forms.ToolStripItem>할당 되어 보다 더 많은 공간을 필요로 하는 s는 <xref:System.Windows.Forms.ToolStrip> 폼의 현재 크기를 지정는 <xref:System.Windows.Forms.ToolStripOverflowButton> 에 자동으로 표시 되는 <xref:System.Windows.Forms.ToolStrip>합니다. <xref:System.Windows.Forms.ToolStripOverflowButton> 표시 되 면 오버플로 드롭다운 메뉴에 오버플로가 활성화 된 항목은 이동 하 고 있습니다. 사용자 지정 하 고 우선 순위를 지정할 수 있습니다 어떻게 프로그램 <xref:System.Windows.Forms.ToolStrip> 항목 다양 한 폼 크기에 맞게 조정 합니다. 사용 하 여 오버플로에 포함 될 경우 해당 항목의 모양을 변경할 수도 있습니다는 <xref:System.Windows.Forms.ToolStripItem.Placement%2A> 및 <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> 속성 및 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> 이벤트입니다. 더 디자인 타임 또는 런타임에 폼을 확대 하는 경우 <xref:System.Windows.Forms.ToolStripItem>s 주에 표시할 수 있으며 <xref:System.Windows.Forms.ToolStrip> 및 <xref:System.Windows.Forms.ToolStripOverflowButton> 폼의 크기를 줄일 때까지 않을 수도 있습니다.  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a>ToolStrip 컨트롤에서 오버플로 사용 하도록 설정 하려면  
  
-   확인은 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 속성으로 설정 되지 않은 `false` 에 대 한는 <xref:System.Windows.Forms.ToolStrip>합니다. 기본값은 `True`입니다.  
  
     때 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> 은 `True` (기본값) 이면는 <xref:System.Windows.Forms.ToolStripItem> 드롭 다운 오버플로 메뉴로 보낼 때의 콘텐츠는 <xref:System.Windows.Forms.ToolStripItem> 가로 너비를 초과 <xref:System.Windows.Forms.ToolStrip> 또는 세로 높이 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>특정 ToolStripItem의 오버플로 동작을 지정 하려면  
  
-   설정의 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> 의 속성에서 <xref:System.Windows.Forms.ToolStripItem> 을 원하는 값입니다. 이 속성은 `Always`, `Never`, 및 `AsNeeded`합니다. defaultis `AsNeeded`합니다.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
