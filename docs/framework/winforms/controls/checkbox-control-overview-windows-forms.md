---
title: "CheckBox 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "CheckBox"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "바인딩 컨트롤, 확인란"
  - "확인란, 확인란 정보"
  - "CheckBox 컨트롤[Windows Forms], CheckBox 컨트롤 정보"
  - "데이터 바인딩, checkbox 컨트롤"
  - "데이터 바인딩 컨트롤, 확인란"
ms.assetid: 085a4e0b-9046-473f-b141-d0edddfb2ebb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# CheckBox 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.CheckBox> 컨트롤은 특정 조건의 설정 또는 해제를 나타냅니다.  일반적으로 이 컨트롤은 사용자에게 Yes\/No 또는 True\/False 선택을 제공하는 데 사용됩니다.  CheckBox 컨트롤을 그룹으로 사용하여 여러 개의 선택을 표시하고 그 중 하나 이상을 선택하도록 할 수 있습니다.  
  
 확인란 컨트롤은 라디오 단추 컨트롤과 비슷하며 두 컨트롤 모두 사용자의 선택을 나타나는 데 사용됩니다.  그러나 라디오 단추의 경우 하나의 그룹에서 한 번에 하나의 단추만 선택할 수 있고,  확인란 컨트롤의 경우 여러 개의 확인란을 선택할 수 있다는 점이 다릅니다.  
  
 간단한 데이터 바인딩을 사용하면 확인란을 데이터베이스의 요소에 연결할 수 있습니다.  <xref:System.Windows.Forms.GroupBox> 컨트롤을 사용하면 여러 개의 확인란을 그룹화할 수 있습니다.  그룹화된 컨트롤은 폼 디자이너에서 함께 이동할 수 있으므로 시각적으로 보기 좋으며 사용자 인터페이스 디자인에도 유용합니다.  자세한 내용은 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md) 및 [GroupBox 컨트롤](../../../../docs/framework/winforms/controls/groupbox-control-windows-forms.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.CheckBox> 컨트롤은 <xref:System.Windows.Forms.CheckBox.Checked%2A>와 <xref:System.Windows.Forms.CheckBox.CheckState%2A>라는 두 개의 중요한 속성을 가지고 있습니다.  <xref:System.Windows.Forms.CheckBox.Checked%2A> 속성은 `true` 또는 `false`를 반환합니다.  <xref:System.Windows.Forms.CheckBox.CheckState%2A> 속성은 <xref:System.Windows.Forms.CheckState> 또는 <xref:System.Windows.Forms.CheckState>를 반환합니다. <xref:System.Windows.Forms.CheckBox.ThreeState%2A> 속성이 `true`로 설정되어 있는 경우에는 <xref:System.Windows.Forms.CheckBox.CheckState%2A>가 <xref:System.Windows.Forms.CheckState>를 반환할 수도 있습니다.  비활성화된 상태에서는 상자가 흐릿하게 표시되어 해당 옵션을 사용할 수 없음을 나타냅니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.CheckBox>   
 [방법: Windows Forms CheckBox 컨트롤을 사용하여 옵션 설정](../../../../docs/framework/winforms/controls/how-to-set-options-with-windows-forms-checkbox-controls.md)   
 [방법: Windows Forms CheckBox 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-checkbox-clicks.md)   
 [CheckBox 컨트롤](../../../../docs/framework/winforms/controls/checkbox-control-windows-forms.md)