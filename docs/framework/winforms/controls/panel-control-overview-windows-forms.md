---
title: "Panel 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "Panel"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "컨트롤 그룹화, Panel 컨트롤"
  - "Panel 컨트롤[Windows Forms], Panel 컨트롤 정보"
ms.assetid: b6b83636-2c39-4dad-89d6-f0fa41049a74
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Panel 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Panel> 컨트롤은 다른 컨트롤을 구별할 수 있도록 그룹화하는 데 사용됩니다.  일반적으로 폼을 기능별로 구분하기 위해 패널을 사용합니다.  예를 들면 사용할 야간 운송 수단과 같은 우편물 옵션을 지정하는 주문 양식을 만들 수 있습니다.  모든 옵션을 하나의 패널로 그룹화하면 논리적이고 시각적인 방식으로 옵션을 이해할 수 있습니다.  또한 디자인 타임에 모든 컨트롤을 쉽게 이동할 수 있습니다. <xref:System.Windows.Forms.Panel> 컨트롤을 이동하면 여기에 포함된 모든 컨트롤도 함께 이동됩니다.  <xref:System.Windows.Forms.Control.Controls%2A> 속성을 사용하면 패널에 그룹화된 컨트롤에 액세스할 수 있습니다.  이 속성은 <xref:System.Windows.Forms.Control> 인스턴스의 컬렉션을 반환하므로 일반적으로 이 방식을 통해 가져온 컨트롤을 특정 형식으로 캐스팅해야 합니다.  
  
## Panel 컨트롤과 GroupBox 컨트롤  
 <xref:System.Windows.Forms.Panel> 컨트롤은 <xref:System.Windows.Forms.GroupBox> 컨트롤과 비슷하지만 <xref:System.Windows.Forms.Panel> 컨트롤에만 스크롤 막대가 있고 <xref:System.Windows.Forms.GroupBox> 컨트롤에만 캡션을 표시할 수 있다는 점이 다릅니다.  
  
## 키 속성  
 스크롤 막대를 표시하려면 <xref:System.Windows.Forms.ScrollableControl.AutoScroll%2A> 속성을 `true`로 설정합니다.  또한 <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.BackgroundImage%2A> 및 <xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성을 설정하여 패널의 모양을 사용자 지정할 수도 있습니다.  <xref:System.Windows.Forms.Control.BackColor%2A> 및 <xref:System.Windows.Forms.Control.BackgroundImage%2A> 속성에 대한 자세한 내용은 [방법: 패널의 배경 설정](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel.md)을 참조하십시오.  <xref:System.Windows.Forms.Panel.BorderStyle%2A> 속성은 패널의 윤곽선을 그릴 때 테두리를 표시하지 않거나\(<xref:System.Windows.Forms.BorderStyle>\), 단선으로 표시하거나\(<xref:System.Windows.Forms.BorderStyle>\), 음영선으로 표시하도록\(<xref:System.Windows.Forms.BorderStyle>\) 지정합니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Panel>   
 [GroupBox 컨트롤](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)   
 [방법: 디자이너에서 Windows Forms 패널 컨트롤을 사용하여 컨트롤 그룹화](../../../../docs/framework/winforms/controls/group-controls-with-wf-panel-control-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms 패널의 배경 설정](../../../../docs/framework/winforms/controls/how-to-set-the-background-of-a-windows-forms-panel-using-the-designer.md)