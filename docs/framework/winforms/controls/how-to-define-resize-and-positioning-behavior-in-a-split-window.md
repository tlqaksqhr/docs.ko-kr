---
title: "방법: 분할 창에서 크기 조정 및 위치 지정 동작 정의 | Microsoft Docs"
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
  - "분할 창, 크기 조정"
  - "SplitContainer 컨트롤[Windows Forms], 크기 조정"
  - "분할 창, 크기 조정"
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 분할 창에서 크기 조정 및 위치 지정 동작 정의
<xref:System.Windows.Forms.SplitContainer> 컨트롤의 패널에서 사용자는 크기를 조정하고 조작할 수 있습니다.  그러나 분할자의 위치 또는 이동하는 범위 등을 프로그래밍 방식으로 제어해야 하는 경우가 있습니다.  
  
 <xref:System.Windows.Forms.SplitContainer> 컨트롤의 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성과 다른 속성을 사용하여 사용자 인터페이스의 동작을 필요에 맞게 세밀하게 제어할 수 있습니다.  이들 속성은 아래의 표에 나열되어 있습니다.  
  
|Name|설명|  
|----------|--------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> 속성|분할자를 키보드로 이동할지 아니면 마우스로 이동할지 여부를 결정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> 속성|왼쪽 또는 위쪽 가장자리에서 이동 가능한 분할 막대까지의 거리를 픽셀 단위로 지정합니다.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성|사용자가 분할자를 이동할 수 있는 최소 거리를 픽셀 단위로 지정합니다.|  
  
 다음 예제에서는 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성을 수정하여 "분할자 맞춤" 효과를 냅니다. 즉, 사용자가 분할자를 끌면 기본값인 1픽셀이 아니라 10픽셀 단위로 증가합니다.  
  
### SplitContainer 크기 조정 동작을 정의하려면  
  
1.  분할자의 '맞춤' 동작이 이루어지도록 프로시저에서 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> 속성을 원하는 크기로 설정합니다.  
  
     다음 코드 예제에서는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에서 <xref:System.Windows.Forms.SplitContainer> 컨트롤 내의 분할자를 끌 때 10픽셀을 이동하도록 설정합니다.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     분할자를 왼쪽이나 오른쪽으로 조금 움직일 때는 커다란 효과가 없지만 마우스 포인터를 10픽셀 이동하면 분할자가 새 위치로 맞춰집니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.SplitContainer>   
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>