---
title: "Windows Forms 컨트롤의 속성 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 속성"
  - "사용자 지정 컨트롤[Windows Forms], 속성 개요(코드 사용)"
  - "속성[Windows Forms]"
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Windows Forms 컨트롤의 속성
Windows Forms 컨트롤은 기본 클래스 <xref:System.Windows.Forms.Control?displayProperty=fullName>에서 많은 속성을 상속합니다.  이러한 속성으로는 <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>와 같은 속성과 기타 많은 속성이 있습니다.  상속되는 속성에 대한 자세한 내용은 <xref:System.Windows.Forms.Control?displayProperty=fullName>을 참조하십시오.  
  
 속성을 새로 정의할 수 있을 뿐만 아니라 컨트롤에서 상속된 속성을 재정의할 수도 있습니다.  
  
## 단원 내용  
 [속성 정의](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 사용자 지정 컨트롤이나 구성 요소의 속성을 구현하는 방법과 속성을 디자인 환경에 통합하는 방법을 보여 줍니다.  
  
 [ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 사용자 지정 컨트롤이나 구성 요소의 기본 속성 값을 정의하는 방법을 보여 줍니다.  
  
 [속성 변경 이벤트](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 속성 값이 바뀔 때 속성 변경 알림을 활성화하는 방법을 설명합니다.  
  
 [방법: 구성 요소 컨트롤의 속성 노출](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 사용자 지정 복합 컨트롤에 있는 구성 요소 컨트롤의 속성을 노출하는 방법을 보여 줍니다.  
  
 [사용자 지정 컨트롤에서 메서드 구현](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 사용자 지정 컨트롤 및 구성 요소에서 메서드를 구현하는 방법을 설명합니다.  
  
## 참조  
 <xref:System.Windows.Forms.UserControl>  
 복합 컨트롤을 구현하는 데 필요한 기본 클래스에 대해 설명합니다.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 사용자 지정 속성 형식으로 사용할 <xref:System.ComponentModel.TypeConverter>를 지정하는 특성에 대해 설명합니다.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 사용자 지정 속성에 사용할 <xref:System.Drawing.Design.UITypeEditor>를 지정하는 특성에 대해 설명합니다.  
  
## 관련 단원  
 [Windows Forms 컨트롤의 특성](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 사용자 지정 컨트롤 및 구성 요소의 속성이나 다른 멤버에 적용할 수 있는 특성을 설명합니다.  
  
 [구성 요소의 디자인 타임 특성](../Topic/Design-Time%20Attributes%20for%20Components.md)  
 디자인 타임에 비주얼 디자이너에서 제대로 표시되도록 구성 요소와 컨트롤에 적용할 메타데이터 특성을 나열합니다.  
  
 [Extending Design\-Time Support](../Topic/Extending%20Design-Time%20Support.md)  
 디자인 타임에 지원하는 편집기나 디자이너 같은 클래스를 구현하는 방법을 설명합니다.