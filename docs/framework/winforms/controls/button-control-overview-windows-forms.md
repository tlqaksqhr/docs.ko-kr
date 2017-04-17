---
title: "Button 컨트롤 개요(Windows Forms) | Microsoft Docs"
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
  - "Button"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Button 컨트롤[Windows Forms], Button 컨트롤 정보"
  - "단추, 단추 정보"
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Button 컨트롤 개요(Windows Forms)
Windows Forms <xref:System.Windows.Forms.Button> 컨트롤을 사용하면 사용자가 단추를 클릭했을 때 특정 동작이 수행되도록 할 수 있습니다.  단추를 클릭하면 단추를 눌렀다 놓은 것처럼 보입니다.  단추를 클릭할 때마다 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기가 호출됩니다.  선택한 동작을 수행하려면 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 해당 코드를 작성합니다.  
  
 단추에 표시되는 텍스트는 <xref:System.Windows.Forms.Control.Text%2A> 속성에 포함되어 있습니다.  텍스트 길이가 단추의 폭을 초과할 경우 다음 줄로 넘어 갑니다.  그러나 컨트롤이 텍스트의 전체 높이를 수용할 수 없는 경우 텍스트가 잘립니다.  자세한 내용은 [방법: Windows Forms 컨트롤에서 표시하는 텍스트 설정](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)를 참조하십시오.  <xref:System.Windows.Forms.Control.Text%2A> 속성은 선택키를 포함할 수 있습니다. Alt 키와 함께 선택키를 누르면 컨트롤을 "클릭"하는 것과 같은 결과를 얻을 수 있습니다.  자세한 내용은 [방법: Windows Forms 컨트롤에 대한 선택키 만들기](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)를 참조하십시오.  텍스트의 모양은 <xref:System.Windows.Forms.Control.Font%2A> 속성 및 <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> 속성으로 제어합니다.  
  
 <xref:System.Windows.Forms.Button> 컨트롤은 <xref:System.Windows.Forms.ButtonBase.Image%2A> 및 <xref:System.Windows.Forms.ButtonBase.ImageList%2A> 속성을 사용하여 이미지를 표시할 수도 있습니다.  자세한 내용은 [방법: Windows Forms 컨트롤에서 표시하는 이미지 설정](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Button>   
 [방법: Windows Forms 단추 클릭에 응답](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Windows Forms Button 컨트롤 선택 방법](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [방법: 디자이너를 사용하여 Windows Forms 단추를 적용 단추로 지정](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [방법: 디자이너를 사용하여 Windows Forms 단추를 취소 단추로 지정](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)   
 [Button 컨트롤](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)