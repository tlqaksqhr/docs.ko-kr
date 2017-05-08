---
title: "방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정 | Microsoft Docs"
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
  - "데이터 표, 데이터 정렬"
  - "DataGridView 컨트롤[Windows Forms], 정렬 모드"
  - "정렬, 데이터 표"
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms DataGridView 컨트롤의 열 정렬 모드 설정
<xref:System.Windows.Forms.DataGridView> 컨트롤의 텍스트 상자 열에서는 기본적으로 자동 정렬되지만 다른 열 형식은 자동으로 정렬되지 않습니다.  이러한 기본값을 재정의할 수 있습니다.  예를 들어, 텍스트, 번호 또는 열거형 셀 값 대신 이미지를 표시할 수 있습니다.  이미지는 정렬할 수 없지만 이미지가 나타내는 내부 값은 정렬할 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에서 열의 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> 속성 값은 열의 정렬 동작을 결정합니다.  
  
 다음 절차에서는 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)의 `Priority` 열을 보여 줍니다.  이 열은 이미지 열이므로 기본적으로 정렬될 수 없습니다.  그러나 이 열에는 문자열인 실제 셀 값을 포함하므로 열이 자동으로 정렬될 수 있습니다.  
  
### 열에 대한 정렬 모드를 설정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName> 속성을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `Priority`라는 열을 포함하는 `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 데이터 정렬](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 열 정렬 모드](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 정렬 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)