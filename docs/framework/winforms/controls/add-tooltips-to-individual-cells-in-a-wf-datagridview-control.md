---
title: "방법: Windows Forms DataGridView 컨트롤에서 개별 셀에 도구 설명 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "데이터 표, 도구 설명 추가"
  - "DataGridView 컨트롤[Windows Forms], 도구 설명 추가"
  - "도구 설명[Windows Forms], 데이터 표에 추가"
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms DataGridView 컨트롤에서 개별 셀에 도구 설명 추가
기본적으로 도구 설명은 크기가 너무 작아서 전체 내용을 표시할 수 없는 <xref:System.Windows.Forms.DataGridView> 셀의 값을 표시하는 데 사용됩니다.  그러나 이 동작을 재정의하여 개별 셀에 대한 도구 설명 텍스트 값을 설정할 수 있습니다.  이는 셀에 대한 추가 정보를 표시하거나 셀 내용에 대한 대체 설명을 제공하는 데 유용합니다.  예를 들어, 상태 아이콘을 표시하는 행이 있는 경우 도구 설명을 사용하여 텍스트 설명을 제공할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName> 속성을 `false`로 설정하여 셀 수준 도구 설명 표시를 비활성화할 수도 있습니다.  
  
### 셀에 도구 설명을 추가하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName> 속성을 설정합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## 코드 컴파일  
  
-   이 예제에는 다음 사항이 필요합니다.  
  
-   네 개의 별표\("\*"\) 기호를 통해 문자열 값을 표시하는 `Rating` 열을 포함하고 `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤.  컨트롤의 <xref:System.Windows.Forms.DataGridView.CellFormatting> 이벤트를 예제에 표시된 이벤트 처리기 메서드에 연결해야 합니다.  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 강력한 프로그래밍  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 외부 데이터 소스에 바인딩하거나 가상 모드를 구현하여 사용자 데이터 소스를 제공하면 성능 문제가 발생할 수 있습니다.  대용량 데이터에 대한 작업을 수행할 때 성능 저하를 방지하려면 여러 셀의 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 속성을 설정하는 대신 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> 이벤트를 처리합니다.  이 이벤트를 처리할 때 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> 셀 속성 값을 가져오면 이벤트가 발생하고 이벤트 처리기에 지정된 <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=fullName> 속성 값이 반환됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCell>   
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)