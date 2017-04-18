---
title: "방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤 | Microsoft Docs"
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
  - "사용자 지정 컨트롤[Windows Forms], 디자이너를 사용하여 도킹"
  - "Dock 속성, 컨트롤 맞춤(디자이너 사용)"
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 디자인 타임에 컨트롤을 폼의 가장자리에 맞춤
<xref:System.Windows.Forms.Control.Dock%2A>을 설정하여 컨트롤을 폼 가장자리에 맞춰 정렬할 수 있습니다.  이 속성에서는 폼에서 컨트롤의 위치를 지정합니다.  <xref:System.Windows.Forms.Control.Dock%2A> 속성을 다음과 같은 값으로 설정할 수 있습니다.  
  
|설정|컨트롤에 미치는 영향|  
|--------|-----------------|  
|<xref:System.Windows.Forms.DockStyle>|컨트롤을 폼 아래쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle>|폼의 나머지 공백을 모두 채웁니다.|  
|<xref:System.Windows.Forms.DockStyle>|컨트롤을 폼의 왼쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle>|컨트롤을 도킹하지 않고 <xref:System.Windows.Forms.Control.Location%2A>에 지정된 위치에 표시합니다.|  
|<xref:System.Windows.Forms.DockStyle>|컨트롤을 폼의 오른쪽에 도킹합니다.|  
|<xref:System.Windows.Forms.DockStyle>|컨트롤을 폼의 맨 위쪽에 도킹합니다.|  
  
 이러한 값을 코드에서 설정할 수도 있습니다.  자세한 내용은 [방법: 컨트롤을 폼의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)을 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 디자인 타임에 컨트롤의 Dock 속성을 설정하려면  
  
1.  Windows Forms 디자이너에서 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.Control.Dock%2A> 속성 옆의 드롭다운 상자를 클릭합니다.  
  
     그래픽 인터페이스에 여섯 개의 사용 가능한 <xref:System.Windows.Forms.Control.Dock%2A> 설정이 표시됩니다.  
  
3.  적절한 설정을 선택합니다.  
  
4.  이제 설정을 통해 지정된 방식대로 컨트롤이 도킹됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=fullName>   
 [방법: 컨트롤을 폼의 가장자리에 맞춤](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)   
 [연습: 맞춤선을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)   
 [방법: Windows Forms에서 컨트롤 고정](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)   
 [방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)   
 [방법: FlowLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)   
 [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)   
 [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)   
 [디자인할 때 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)