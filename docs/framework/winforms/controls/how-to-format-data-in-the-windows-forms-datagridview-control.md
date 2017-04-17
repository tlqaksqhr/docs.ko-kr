---
title: "방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정 | Microsoft Docs"
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
  - "셀, 텍스트 맞춤"
  - "통화 값, 데이터 표에서 형식 지정"
  - "데이터[Windows Forms], DataGridView 컨트롤에서 형식 지정"
  - "데이터 표, 통화 값"
  - "데이터 표, 날짜 값"
  - "데이터 표, 단어 잘림 방지 사용"
  - "데이터 표, 데이터 서식 지정"
  - "데이터 표, 텍스트 맞춤"
  - "DataGridView 컨트롤[Windows Forms], 데이터 서식 지정"
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정
다음 프로시저에서는 <xref:System.Windows.Forms.DataGridView> 컨트롤 및 컨트롤에 있는 특정 열의 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> 속성을 사용하여 셀 값에 기본적인 형식을 지정하는 방법을 보여 줍니다.  고급 데이터 형식 지정에 대한 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
### 통화 및 날짜 값의 형식을 지정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성을 설정합니다.  다음 코드 예제에서는 열의 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성을 사용하여 특정 열의 형식을 설정합니다.   `UnitPrice` 열의 값은 현재 문화권별 통화 형식으로 나타나며 음수는 괄호로 묶입니다.   `ShipDate` 열의 값은 현재 문화권별 간단한 날짜 형식으로 나타납니다.  <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 값에 대한 자세한 내용은 [형식 서식 지정](../../../../docs/standard/base-types/formatting-types.md)을 참조하십시오.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### null 데이터베이스 값의 표시를 사용자 지정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> 속성을 설정합니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> 속성을 사용하여 <xref:System.DBNull.Value?displayProperty=fullName>와 같은 값을 포함하는 모든 셀에 "no entry"를 표시합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### 텍스트 기반 셀에 단어 잘림 방지를 사용하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> 속성을 <xref:System.Windows.Forms.DataGridViewTriState> 열거형 값 중 하나로 설정합니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> 속성을 사용하여 전체 컨트롤에 대해 줄 바꿈 모드를 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### DataGridView 셀의 텍스트 맞춤을 지정하려면  
  
-   <xref:System.Windows.Forms.DataGridViewCellStyle>의 <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> 속성을 <xref:System.Windows.Forms.DataGridViewContentAlignment> 열거형 값 중 하나로 설정합니다.  다음 코드 예제에서는 열의 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성을 사용하여 특정 열에 맞춤을 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `UnitPrice`, `ShipDate` 및 `CustomerName`이라는 열을 포함하는 이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 강력한 프로그래밍  
 확장성을 최대화하려면 각 요소에 대해 개별적으로 스타일 속성을 설정하는 대신 동일한 스타일을 사용하는 여러 행, 열 또는 셀에서 <xref:System.Windows.Forms.DataGridViewCellStyle> 개체를 공유해야 합니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 크기를 조정하는 최선의 방법](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)   
 [형식 서식 지정](../../../../docs/standard/base-types/formatting-types.md)