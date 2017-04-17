---
title: "방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정 | Microsoft Docs"
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
  - "데이터 표, 행 사용자 지정"
  - "DataGridView 컨트롤[Windows Forms], 행 사용자 지정"
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정
<xref:System.Windows.Forms.DataGridView> 컨트롤은 데이터 바인딩을 통해 또는 사용할 기존 행을 지정하지 않고 <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=fullName> 메서드를 호출하여 컨트롤에 추가하는 모든 행의 기반으로 행 템플릿을 사용합니다.  
  
 행 템플릿을 사용하면 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> 속성을 사용하는 것보다 행의 모양과 동작을 보다 효과적으로 제어할 수 있습니다.  행 템플릿에 대해 <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>을 포함한 모든 <xref:System.Windows.Forms.DataGridViewRow> 속성을 설정할 수 있습니다.  
  
 특정 효과를 얻기 위해 행 템플릿을 사용해야 하는 경우도 있습니다.  예를 들어, 행 높이 정보는 <xref:System.Windows.Forms.DataGridViewCellStyle>에 저장할 수 없으므로 행 템플릿을 사용하여 모든 행에 사용되는 기본 높이를 변경해야 합니다.  또한 행 템플릿은 <xref:System.Windows.Forms.DataGridViewRow>에서 파생된 사용자 클래스를 만드는 경우와 새 행을 컨트롤에 추가할 때 사용자 지정 형식을 사용하려는 경우 유용합니다.  
  
> [!NOTE]
>  행 템플릿은 행을 추가할 때만 사용됩니다.  행 템플릿을 변경하여 기존 행을 변경할 수 없습니다.  
  
### 행 템플릿을 사용하려면  
  
-   <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName> 속성에서 검색된 개체의 속성을 설정합니다.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridViewRow>   
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 기본 형식 및 스타일 지정](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)