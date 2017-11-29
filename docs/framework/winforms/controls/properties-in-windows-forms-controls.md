---
title: "Windows Forms 컨트롤의 속성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], properties overview (using code)
- controls [Windows Forms], properties
- properties [Windows Forms]
ms.assetid: 2785279b-fb57-4937-8f6b-2050e475db6f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d5de09635fb92b46a2c0f89427ad03449de6bd53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="properties-in-windows-forms-controls"></a>Windows Forms 컨트롤의 속성
Windows Forms 컨트롤 속성 폼을 여러 기본 클래스를 상속 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다. 여기에 속성 같은 <xref:System.Windows.Forms.Control.Font%2A>, <xref:System.Windows.Forms.Control.ForeColor%2A>, <xref:System.Windows.Forms.Control.BackColor%2A>, <xref:System.Windows.Forms.Control.Bounds%2A>, <xref:System.Windows.Forms.Control.ClientRectangle%2A>, <xref:System.Windows.Forms.Control.DisplayRectangle%2A>, <xref:System.Windows.Forms.Control.Enabled%2A>, <xref:System.Windows.Forms.Control.Focused%2A>, <xref:System.Windows.Forms.Control.Height%2A>, <xref:System.Windows.Forms.Control.Width%2A>, <xref:System.Windows.Forms.Control.Visible%2A>, <xref:System.Windows.Forms.Control.AutoSize%2A>, 및 다른 많은 요인을 합니다. 상속 된 속성에 대 한 세부 정보를 참조 하십시오. <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.  
  
 컨트롤에서 상속된 속성을 재정의하고 새 속성을 정의할 수도 있습니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [속성 정의](../../../../docs/framework/winforms/controls/defining-a-property-in-windows-forms-controls.md)  
 사용자 지정 컨트롤 또는 구성 요소에 대한 속성을 구현하는 방법 및 속성을 디자인 환경으로 통합하는 방법을 보여 줍니다.  
  
 [ShouldSerialize 및 Reset 메서드를 사용하여 기본값 정의](../../../../docs/framework/winforms/controls/defining-default-values-with-the-shouldserialize-and-reset-methods.md)  
 사용자 지정 컨트롤 또는 구성 요소에 대한 기본 속성 값을 정의하는 방법을 보여 줍니다.  
  
 [속성 변경 이벤트](../../../../docs/framework/winforms/controls/property-changed-events.md)  
 속성 값이 변경될 때 속성 변경 알림을 활성화하는 방법을 설명합니다.  
  
 [방법: 구성 요소 컨트롤의 속성 노출](../../../../docs/framework/winforms/controls/how-to-expose-properties-of-constituent-controls.md)  
 사용자 지정 복합 컨트롤에서 구성 요소 컨트롤의 속성을 노출하는 방법을 보여 줍니다.  
  
 [사용자 지정 컨트롤에서 메서드 구현](../../../../docs/framework/winforms/controls/method-implementation-in-custom-controls.md)  
 사용자 지정 컨트롤 및 구성 요소에서 메서드를 구현하는 방법을 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.Windows.Forms.UserControl>  
 복합 컨트롤을 구현하기 위한 기본 클래스를 설명합니다.  
  
 <xref:System.ComponentModel.TypeConverterAttribute>  
 지정 하는 특성에 설명 된 <xref:System.ComponentModel.TypeConverter> 사용자 지정 속성 형식에 대해 사용 하도록 합니다.  
  
 <xref:System.ComponentModel.EditorAttribute>  
 지정 하는 특성에 설명 된 <xref:System.Drawing.Design.UITypeEditor> 사용자 지정 속성에 사용할 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [Windows Forms 컨트롤의 특성](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
 사용자 지정 컨트롤 및 구성 요소의 속성이나 다른 멤버에 적용할 수 있는 특성을 설명합니다.  
  
 [구성 요소의 디자인 타임 특성](http://msdn.microsoft.com/library/12050fe3-9327-4509-9e21-4ee2494b95c3)  
 비주얼 디자이너에서 디자인 타임에 올바르게 표시되도록 구성 요소 및 컨트롤에 적용할 메타데이터 특성을 나열합니다.  
  
 [디자인 타임 지원 확장](http://msdn.microsoft.com/library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)  
 디자인 타임 지원을 제공하는 편집기 및 디자이너와 같은 클래스를 구현하는 방법을 설명합니다.
