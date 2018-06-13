---
title: '방법: Windows Forms에 컨트롤 도킹'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: 6cb4c982cb4c9e2df8d0335738ca087733209bdc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532325"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>방법: Windows Forms에 컨트롤 도킹
폼의 가장자리에 컨트롤을 도킹 하거나 컨트롤의 컨테이너 (폼 또는 컨테이너 컨트롤)을 채울 수 있습니다. Windows 탐색기 창을 도킹 하는 예를 들어 해당 <xref:System.Windows.Forms.TreeView> 컨트롤 창의 왼쪽 가장자리와 해당 <xref:System.Windows.Forms.ListView> 컨트롤 창의 왼쪽에서 오른쪽으로 합니다. 사용 된 <xref:System.Windows.Forms.Control.Dock%2A> 표시 하는 모든 Windows Forms 컨트롤 도킹 모드를 정의 하는 속성입니다.  
  
> [!NOTE]
>  역방향 z-순서에 컨트롤 도킹 됩니다.  
  
 <xref:System.Windows.Forms.Control.Dock%2A> 속성와 상호 작용 하는 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성입니다. 자세한 내용은 참조 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)합니다.  
  
### <a name="to-dock-a-control"></a>컨트롤을 도킹 하려면  
  
1.  컨트롤을 도킹 하려면 선택 합니다.  
  
2.  속성 창에서 오른쪽의 화살표를 클릭 하 고 <xref:System.Windows.Forms.Control.Dock%2A> 속성입니다.  
  
     일련의 가장자리와 폼의 중심을 나타내는 상자를 표시 하는 편집기가 표시 됩니다.  
  
3.  도킹 된 컨트롤을 폼의 가장자리를 나타내는 단추를 클릭 합니다. 컨트롤의 폼 이나 컨테이너 컨트롤의 내용을 채울 센터 상자를 클릭 합니다. 클릭 **(없음)** 도킹 하지 않으려면입니다.  
  
     컨트롤은 자동으로 도킹된 된 가장자리의 경계에 맞게 크기가 조정 됩니다.  
  
    > [!NOTE]
    >  상속 된 컨트롤 이어야 합니다 `Protected` 도킹 될 수 있습니다. 컨트롤의 액세스 수준을 변경 하려면 해당 **한정자** 속성 창에서 속성입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/index.md)  
 [Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Windows Forms에 사용할 수 있는 컨트롤](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [기능별 Windows Forms 컨트롤](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [방법: Windows Forms에서 컨트롤 고정](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
