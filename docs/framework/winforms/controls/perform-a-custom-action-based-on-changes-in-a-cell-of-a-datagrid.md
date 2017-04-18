---
title: "방법: Windows Forms DataGridView 컨트롤의 셀 변경 내용에 따라 사용자 지정 작업 수행 | Microsoft Docs"
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
  - "셀, 변경 내용 감지"
  - "데이터 표, 셀 변경 내용 감지"
  - "DataGridView 컨트롤[Windows Forms], 셀 변경 내용 감지"
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms DataGridView 컨트롤의 셀 변경 내용에 따라 사용자 지정 작업 수행
<xref:System.Windows.Forms.DataGridView> 컨트롤에는 <xref:System.Windows.Forms.DataGridView> 셀의 상태 변경을 검색하는 데 사용할 수 있는 많은 이벤트가 포함되어 있습니다.  가장 일반적으로 사용되는 두 가지 이벤트는 <xref:System.Windows.Forms.DataGridView.CellValueChanged> 이벤트와 <xref:System.Windows.Forms.DataGridView.CellStateChanged> 이벤트입니다.  
  
### DataGridView 셀의 값 변경을 검색하려면  
  
-   <xref:System.Windows.Forms.DataGridView.CellValueChanged> 이벤트에 대한 처리기를 작성합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### DataGridView 셀의 상태 변경을 검색하려면  
  
-   <xref:System.Windows.Forms.DataGridView.CellStateChanged> 이벤트에 대한 처리기를 작성합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  C\#의 경우 이벤트 처리기가 해당 이벤트에 연결되어 있어야 합니다.  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤에서 셀, 행 및 열 프로그래밍](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)   
 [연습: Windows Forms DataGridView 컨트롤의 데이터 유효성 검사](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)