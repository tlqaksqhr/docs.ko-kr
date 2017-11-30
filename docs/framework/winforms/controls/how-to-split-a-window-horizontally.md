---
title: "방법: 가로로 창 분할"
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
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 02133cc38221b23ea1e2b14bfd0bbcf1987ab532
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-split-a-window-horizontally"></a>방법: 가로로 창 분할
다음 코드 예제에서는 나누는 분할자를 사용 하면는 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 가로로 합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 의 속성은 <xref:System.Windows.Forms.SplitContainer> 컨트롤 컨트롤 자체 아닌 분할자의 방향을 결정 합니다.  
  
### <a name="to-split-a-window-horizontally"></a>가로로 창 분할 하려면  
  
1.  프로시저 내에서 설정할는 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 의 속성은 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 <xref:System.Windows.Forms.Orientation.Horizontal>합니다.  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.SplitContainer>  
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
