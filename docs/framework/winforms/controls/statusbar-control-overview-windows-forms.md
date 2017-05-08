---
title: "StatusBar 컨트롤 개요(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StatusBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "상태 표시줄"
  - "StatusBar 컨트롤[Windows Forms], StatusBar 컨트롤 정보"
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# StatusBar 컨트롤 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤을 유지하도록 선택할 수 있습니다.  
  
 Windows Forms [StatusBar 컨트롤](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md)은 폼에서 영역으로 사용되며 대개 창 아래쪽에 표시됩니다. 응용 프로그램에서 여기에 다양한 종류의 상태 정보를 표시할 수 있습니다.  <xref:System.Windows.Forms.StatusBar> 컨트롤은 상태를 나타내는 텍스트나 아이콘이 표시되는 상태 표시줄 패널 또는 프로세스가 진행 중임을 애니메이션으로 표시하는 일련의 아이콘\(예: [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)]에서 문서가 저장되고 있음을 나타내는 경우\)을 포함할 수 있습니다.  
  
## StatusBar 컨트롤 사용  
 Internet Explorer에서는 마우스를 하이퍼링크 위로 가져가면 상태 표시줄에 해당 페이지의 URL이 표시됩니다. 또한 [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)]에서는 페이지 위치, 구역 위치 및 겹쳐쓰기와 변경 내용 추적 같은 편집 모드에 대한 정보가 상태 표시줄에 제공되고 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서는 도킹 가능한 창을 도킹된 창 또는 부동 창으로 조작하는 방법을 알려 주는 등 상황에 맞는 정보가 상태 표시줄에 제공됩니다.  
  
 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `false`\(기본값\)로 설정하고 상태 표시줄의 <xref:System.Windows.Forms.StatusBar.Text%2A> 속성을 상태 표시줄에 나타낼 텍스트로 설정하면 상태 표시줄에 단일 메시지를 표시할 수 있습니다.  <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성을 `true`로 설정하고 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>의 <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> 메서드를 사용하면 상태 표시줄을 여러 패널로 분할하여 다양한 유형의 정보를 표시할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)