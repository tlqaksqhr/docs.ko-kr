---
title: "ProgressBar 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "ProgressBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Progress 컨트롤, progress 컨트롤 정보"
  - "ProgressBar 컨트롤[Windows Forms], ProgressBar 컨트롤 정보"
ms.assetid: a05d9cba-3a6a-4f8f-94b8-8ec12799fb80
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# ProgressBar 컨트롤 개요(Windows Forms)
> [!IMPORTANT]
>  <xref:System.Windows.Forms.ToolStripProgressBar> 컨트롤은 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.ProgressBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 Windows Forms <xref:System.Windows.Forms.ProgressBar> 컨트롤은 가로 막대에 배열된 사각형의 적정 수를 표시하여 작업 진행률을 나타냅니다.  막대가 모두 채워지면 실행이 완료된 것입니다.  진행률 표시줄은 큰 파일을 로드할 때와 같이 프로세스가 완료될 때까지 기다려야 하는 시간을 알려 주는 데 사용됩니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ProgressBar> 컨트롤은 폼에 가로 방향으로만 배치할 수 있습니다.  
  
## 주요 속성 및 메서드  
 <xref:System.Windows.Forms.ProgressBar> 컨트롤의 주요 속성은 <xref:System.Windows.Forms.ProgressBar.Value%2A>, <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A>입니다.  <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 및 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성에서 진행률 표시줄에 표시되는 최대값과 최소값을 설정합니다.  <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성은 작업 진행률을 나타냅니다.  <xref:System.Windows.Forms.ProgressBar> 컨트롤에 표시되는 막대는 블록으로 구성되어 있기 때문에 이 컨트롤에 의해 표시되는 값은 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 현재 값을 대략적으로만 나타냅니다.  <xref:System.Windows.Forms.ProgressBar> 컨트롤의 크기에 따라 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성은 다음 블록을 표시할 시간을 결정합니다.  
  
 현재 진행률 값을 업데이트하는 가장 일반적인 방법은 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 설정하는 코드를 작성하는 것입니다.  큰 파일을 로드하는 경우 최대값을 파일 크기\(KB 단위\)로 설정할 수 있습니다.  예를 들어, <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 속성을 100으로 설정하면 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 속성은 10으로 설정되고, <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 50으로 설정하면 5개의 사각형이 표시됩니다.  이 수는 표시 가능한 수의 절반입니다.  
  
 그러나 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성을 직접 설정하는 방법 이외에도 <xref:System.Windows.Forms.ProgressBar> 컨트롤에 의해 표시되는 값을 수정할 수 있는 방법이 있습니다.  <xref:System.Windows.Forms.ProgressBar.Step%2A> 속성을 사용하여 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성이 증가되는 단위 값을 지정할 수 있습니다.  그런 다음 <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> 메서드를 호출하면 값이 증가됩니다.  증가 값을 변경하려면 <xref:System.Windows.Forms.ProgressBar.Increment%2A> 메서드를 사용하여 <xref:System.Windows.Forms.ProgressBar.Value%2A> 속성의 증가 값을 지정하면 됩니다.  
  
 현재 작업에 대한 정보를 사용자에게 그래픽으로 알려 주는 또 다른 컨트롤로 <xref:System.Windows.Forms.StatusBar> 컨트롤이 있습니다.  
  
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤에 새로운 기능이 추가된 것으로, 이전 컨트롤을 대체합니다. 그러나 이전 버전과의 호환성 및 앞으로의 사용 가능성을 고려하여 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤을 유지하도록 선택할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.ProgressBar>   
 [ProgressBar 컨트롤](../../../../docs/framework/winforms/controls/progressbar-control-windows-forms.md)