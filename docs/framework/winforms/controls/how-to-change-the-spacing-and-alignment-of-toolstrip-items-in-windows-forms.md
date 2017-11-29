---
title: "방법: Windows Forms에서 ToolStrip 항목의 간격 및 맞춤 변경"
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
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 42ae53e143942201359baebdfa8929647e7e35cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>방법: Windows Forms에서 ToolStrip 항목의 간격 및 맞춤 변경
<xref:System.Windows.Forms.ToolStrip> 컨트롤 크기 조정의 간격 같은 레이아웃 기능을 완벽 하 게 지원 <xref:System.Windows.Forms.ToolStripItem> 의 서로 상대적인, 컨트롤 배열을 컨트롤에 <xref:System.Windows.Forms.ToolStrip>를 기준으로 컨트롤의 간격 및는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
 때문에 기본값인은 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성은 `true`, 컨트롤의 크기가 자동으로 설정 하지 않으면는 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false`합니다.  
  
### <a name="to-manually-size-a-toolstripitem"></a>ToolStripItem의 크기를 수동으로 조정 하려면  
  
1.  설정의 <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> 속성을 `false` 연결 된 컨트롤입니다.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  설정의 <xref:System.Windows.Forms.ToolStripItem.Size%2A> 속성 관련 된 원하는 대로 <xref:System.Windows.Forms.ToolStripItem>합니다.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>ToolStripItem의 간격을 설정 하려면  
  
1.  원하는 값을 픽셀 단위로 삽입의 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 연결된 된 컨트롤의 속성입니다.  
  
     값은 <xref:System.Windows.Forms.ToolStripItem.Margin%2A> 이 순서로 항목과 인접 항목 사이의 간격을 지정 하는 속성: 왼쪽, 위쪽, 오른쪽 및 아래쪽입니다.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>ToolStripItem ToolStrip의 오른쪽에 맞추려면  
  
1.  설정의 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemAlignment.Right> 연결 된 컨트롤입니다. 기본적으로 <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> 로 설정 된 <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, 컨트롤의 왼쪽에 맞춥니다는 <xref:System.Windows.Forms.ToolStrip>합니다.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>ToolStrip에 ToolStrip 항목을 정렬 하려면  
  
-   설정의 <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> 속성의 값을 <xref:System.Windows.Forms.ToolStripLayoutStyle> 원하는 합니다.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.Layout>  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>  
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [ToolStrip 컨트롤 개요](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [ToolStrip 컨트롤 아키텍처](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [ToolStrip 기술 요약](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
