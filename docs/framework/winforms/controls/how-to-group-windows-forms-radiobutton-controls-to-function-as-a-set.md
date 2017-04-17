---
title: "방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 그룹화"
  - "라디오 단추, 그룹화"
  - "RadioButton 컨트롤[Windows Forms], 그룹화"
  - "Windows Forms 컨트롤, 그룹화"
ms.assetid: 58f8fe34-50b7-49d8-a2be-c271be3c6b32
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 기능별로 Windows Forms RadioButton 컨트롤 그룹화
Windows Forms <xref:System.Windows.Forms.RadioButton> 컨트롤은 선택할 수 있는 두 개 이상의 설정을 제공하고 그 중 하나만 프로시저나 개체에 지정할 수 있도록 설계되었습니다.  예를 들어, 하나의 <xref:System.Windows.Forms.RadioButton> 컨트롤 그룹이 주문한 패키지를 운송할 회사들을 표시할 수 있지만 그 중 한 운송 회사만 이용됩니다.  따라서 같은 기능을 가진 그룹의 일부인 경우에도 한 번에 하나의 <xref:System.Windows.Forms.RadioButton> 컨트롤만 선택할 수 있습니다.  
  
 라디오 단추는 <xref:System.Windows.Forms.Panel> 컨트롤, <xref:System.Windows.Forms.GroupBox> 컨트롤 또는 폼과 같은 컨테이너 안에서 그려서 그룹화합니다.  폼에 직접 추가한 모든 라디오 단추는 하나의 그룹이 됩니다.  별도의 그룹을 추가하려면 패널이나 그룹 상자에 배치해야 합니다.  패널 또는 그룹 상자에 대한 자세한 내용은 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md) 또는 [GroupBox 컨트롤 개요](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)를 참조하십시오.  
  
### RadioButton 컨트롤을 다른 그룹과 별도로 기능별로 그룹화하려면  
  
1.  <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 컨트롤을 **도구 상자**의 **Windows Forms** 탭에서 폼으로 끌어 옵니다.  
  
2.  <xref:System.Windows.Forms.GroupBox> 또는 <xref:System.Windows.Forms.Panel> 컨트롤에 <xref:System.Windows.Forms.RadioButton> 컨트롤을 그립니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.RadioButton>   
 [RadioButton 컨트롤 개요](../../../../docs/framework/winforms/controls/radiobutton-control-overview-windows-forms.md)   
 [Panel 컨트롤 개요](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [GroupBox 컨트롤 개요](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [CheckBox 컨트롤 개요](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [RadioButton 컨트롤](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)