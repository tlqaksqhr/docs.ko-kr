---
title: "방법: 가로로 창 분할 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "SplitContainer 컨트롤[Windows Forms], 가로 분할자"
  - "분할 창, 분할자 방향 변경"
  - "분할 창, 가로"
  - "windows, 가로로 분할"
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 가로로 창 분할
다음 코드 예제에서는 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 가로로 나누는 분할자를 만듭니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.SplitContainer> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성은 컨트롤이 아니라 분할자의 방향을 결정합니다.  
  
### 창을 가로로 분할하려면  
  
1.  프로시저 내에서 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 속성을 <xref:System.Windows.Forms.Orientation>로 설정합니다.  
  
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
  
## 참고 항목  
 <xref:System.Windows.Forms.SplitContainer>   
 [SplitContainer 컨트롤](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)