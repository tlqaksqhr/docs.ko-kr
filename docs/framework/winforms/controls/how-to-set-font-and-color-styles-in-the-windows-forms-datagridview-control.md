---
title: "방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정 | Microsoft Docs"
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
  - "데이터 표, 색 스타일"
  - "데이터 표, 셀 사용자 지정"
  - "데이터 표, 글꼴 스타일"
  - "DataGridView 컨트롤[Windows Forms], 셀 사용자 지정"
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms DataGridView 컨트롤의 글꼴 및 색 스타일 설정
<xref:System.Windows.Forms.DataGridViewCellStyle> 클래스의 속성을 설정하여 <xref:System.Windows.Forms.DataGridView> 컨트롤 내에 있는 셀의 모양을 지정할 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 클래스 및 해당 도우미 클래스의 다양한 속성에서 이 클래스의 인스턴스를 검색하거나 이러한 속성에 할당하기 위해 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 인스턴스화할 수 있습니다.  
  
 다음 절차에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 속성을 사용한 셀 모양의 기본 사용자 지정을 보여 줍니다.  컨트롤의 모든 셀은 행, 열 또는 셀 수준에서 재정의되지 않는 한 이 속성을 통해 지정된 스타일을 상속합니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에 기본 셀 스타일 설정](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)을 참조하세요.  <xref:System.Windows.Forms.DataGridViewCellStyle> 클래스의 추가 사용에 대한 자세한 내용은 참고 항목 섹션에 나열된 항목을 참조하세요.  
  
 Visual Studio에서는 이 작업이 광범위하게 지원됩니다.  [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\))을 참조하세요.  
  
### DataGridView 셀에서 사용되는 글꼴을 지정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> 속성을 설정합니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> 속성을 사용하여 전체 컨트롤의 글꼴을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### DataGridView 셀의 전경색과 배경색을 지정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> 속성을 설정합니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> 속성을 사용하여 전체 컨트롤에 대해 이러한 스타일을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### 선택한 DataGridView 셀의 전경색과 배경색을 지정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> 및 <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> 속성을 설정합니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> 속성을 사용하여 전체 컨트롤에 대해 이러한 스타일을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 강력한 프로그래밍  
 최대 확장성을 얻으려면 각 요소에 대한 스타일 속성을 별도로 설정하는 대신 동일한 스타일을 사용하는 여러 행, 열 또는 셀에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 공유해야 합니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)