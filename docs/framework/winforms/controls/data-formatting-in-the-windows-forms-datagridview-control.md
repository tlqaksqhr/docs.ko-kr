---
title: "Windows Forms DataGridView 컨트롤의 데이터 형식 지정 | Microsoft Docs"
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
  - "데이터[Windows Forms], 표에서 형식 지정"
  - "데이터 표, 데이터 서식 지정"
  - "DataGridView 컨트롤[Windows Forms], 데이터 서식 지정"
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Windows Forms DataGridView 컨트롤의 데이터 형식 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤은 부모 열에 표시되는 데이터 형식과 셀 값 간에 자동 변환을 제공합니다.  예를 들어, 텍스트 상자 열에서는 날짜, 시간, 숫자, 열거형 값 등을 문자열로 나타내고 사용자가 입력한 문자열 값을 데이터 저장에 필요한 형식으로 변환합니다.  
  
## DataGridViewCellStyle 클래스를 사용하여 형식 지정  
 <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스를 통해 셀 값의 기본 데이터 형식을 제공합니다.  <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성을 사용하여 [형식 서식 지정](../../../../docs/standard/base-types/formatting-types.md)에 설명된 형식 지정자를 사용해 현재 기본 culture에 대한 날짜, 시간, 숫자 및 열거형 값의 형식을 지정할 수 있습니다.  또한 <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A> 속성을 사용하여 특정 culture에 대해 이러한 값의 형식을 지정할 수 있습니다.  지정된 형식은 데이터를 표시하고 사용자가 지정된 형식으로 입력한 데이터를 구문 분석하는 데 모두 사용됩니다.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스는 단어 잘림 방지, 텍스트 맞춤 및 null 데이터베이스 값의 사용자 지정 표시에 대한 추가 형식 속성을 제공합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## CellFormatting 이벤트를 사용하여 형식 지정  
 기본 형식이 사용자의 요구와 맞지 않는 경우 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName> 이벤트의 처리기에서 사용자 지정 데이터 형식을 제공할 수 있습니다.  처리기에 전달되는 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>에는 처음부터 셀 값을 포함하는 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성이 있습니다.  일반적으로 이 값은 표시 형식으로 자동 변환됩니다.  값을 직접 변환하려면 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성을 표시 형식 값으로 설정합니다.  
  
> [!NOTE]
>  형식 문자열이 셀에 적용되는 경우 <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> 속성이 `true`로 설정되어 있지 않는 한 사용자가 변경한 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성을 재정의합니다.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트는 개별 셀의 <xref:System.Windows.Forms.DataGridViewCellStyle> 속성을 해당 값을 기반으로 설정하려는 경우에도 유용합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
 사용자 지정 값에 대한 기본 구문 분석이 사용자의 요구와 맞지 않는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CellParsing> 이벤트를 처리하여 사용자 지정 구문 분석을 제공할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)