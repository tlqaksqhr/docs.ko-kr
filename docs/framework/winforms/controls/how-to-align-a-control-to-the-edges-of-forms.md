---
title: '방법: 컨트롤을 폼의 가장자리에 맞춤'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dock property [Windows Forms], aligning controls (using code)
- forms [Windows Forms], aligning controls
- controls [Windows Forms], aligning on forms
- custom controls [Windows Forms], docking using code
ms.assetid: 5994cb59-242b-4e75-bd0e-62879c34d702
ms.openlocfilehash: a8571f668de2714511a8732772443a8897043cf2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-align-a-control-to-the-edges-of-forms"></a>방법: 컨트롤을 폼의 가장자리에 맞춤
<xref:System.Windows.Forms.Control.Dock%2A> 속성을 설정하여 양식 가장자리에 맞춰서 컨트롤을 정렬할 수 있습니다. 이 속성은 양식에서 컨트롤의 위치를 지정합니다. <xref:System.Windows.Forms.Control.Dock%2A> 속성은 다음 값으로 설정할 수 있습니다.  
  
|설정|컨트롤에 대한 영향|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|양식의 아래쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle.Fill>|양식의 나머지 공간을 모두 채웁니다.|  
|<xref:System.Windows.Forms.DockStyle.Left>|양식의 왼쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle.None>|도킹하지 않고 <xref:System.Windows.Forms.Control.Location%2A> 속성으로 지정된 위치에 표시합니다.|  
|<xref:System.Windows.Forms.DockStyle.Right>|컨트롤을 양식의 오른쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle.Top>|양식의 위쪽에 도킹합니다.|  
  
 Visual Studio에서는 디자인 타임에 이 기능을 지원합니다.  
  
### <a name="to-set-the-dock-property-for-your-control-at-run-time"></a>런타임에 컨트롤에 대한 Dock 속성을 설정하려면  
  
1.  코드에서 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 적절한 값으로 설정합니다.  
  
    ```vb  
    ' To set the Dock property internally.  
    Me.Dock = DockStyle.Top  
    ' To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top  
    ```  
  
    ```csharp  
    // To set the Dock property internally.  
    this.Dock = DockStyle.Top;  
    // To set the Dock property from another object.  
    UserControl1.Dock = DockStyle.Top;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>  
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [AutoSize 속성 개요](../../../../docs/framework/winforms/controls/autosize-property-overview.md)
