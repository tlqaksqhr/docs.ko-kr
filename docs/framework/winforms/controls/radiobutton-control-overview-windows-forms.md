---
title: "RadioButton 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "RadioButton"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "라디오 단추, 라디오 단추 정보"
  - "라디오 단추, 상태 확인"
  - "RadioButton 컨트롤[Windows Forms], RadioButton 컨트롤 정보"
  - "RadioButton 컨트롤[Windows Forms], 상태 확인"
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# RadioButton 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤을 사용하면 두 개 이상의 항목으로 구성된 집합에서 하나의 항목을 상호 배타적으로 선택하도록 할 수 있습니다.  라디오 단추와 확인란은 유사한 기능을 가지고 있지만 중요한 차이가 있습니다. 라디오 단추는 하나의 그룹에서 한 개만 선택할 수 있습니다.  확인란은 개수에 관계없이 선택할 수 있습니다.  사용자가 하나의 항목만 선택할 수 있도록 하려면 라디오 단추 그룹을 지정합니다.  
  
## 컨트롤 사용  
 <xref:System.Windows.Forms.RadioButton> 컨트롤을 클릭하면 이 컨트롤의 <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성이 `true`로 설정되고 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 호출됩니다.  <xref:System.Windows.Forms.RadioButton.Checked%2A> 속성의 값이 변경되면 <xref:System.Windows.Forms.RadioButton.CheckedChanged> 이벤트가 발생합니다.  <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> 속성이 `true`\(기본값\)로 설정된 경우 라디오 단추를 선택하면 해당 그룹의 다른 모든 선택 표시가 자동으로 지워집니다.  이 속성은 선택한 라디오 단추가 허용되는 옵션인지 확인하기 위해 유효성 검사 코드를 사용할 경우 대개 `false`로만 설정됩니다.  컨트롤에 표시되는 텍스트는 <xref:System.Windows.Forms.Control.Text%2A> 속성으로 설정하며 이 속성을 사용하여 선택키를 표시할 수 있습니다.  Alt 키와 함께 선택키를 누르면 컨트롤을 "클릭"하는 것과 같은 효과를 나타낼 수 있습니다.  자세한 내용은 [방법: Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) 및 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.RadioButton.Appearance%2A> 속성을 <xref:System.Windows.Forms.Appearance>으로 설정하면 <xref:System.Windows.Forms.RadioButton> 컨트롤이 명령 단추처럼 표시되어 선택되었을 때 눌린 모습으로 나타납니다.  또한 라디오 단추는 <xref:System.Windows.Forms.ButtonBase.Image%2A> 및 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 속성을 사용하여 이미지를 표시할 수 있습니다.  자세한 내용은 [방법: Windows Forms 컨트롤에서 표시하는 이미지 설정](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RadioButton>   
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [GroupBox 컨트롤 개요](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [CheckBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [방법: Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)   
 [RadioButton 컨트롤](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)