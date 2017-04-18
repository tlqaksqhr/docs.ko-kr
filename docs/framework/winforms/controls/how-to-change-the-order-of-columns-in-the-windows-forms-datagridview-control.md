---
title: "방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경 | Microsoft Docs"
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
  - "열[Windows Forms], 순서 변경"
  - "데이터 표, 열 순서 변경"
  - "DataGridView 컨트롤[Windows Forms], 열 순서"
ms.assetid: 5e9ac3bc-b0f0-48cb-a3d5-b005af905395
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Forms DataGridView 컨트롤에서 열 순서 변경
<xref:System.Windows.Forms.DataGridView>를 사용하여 데이터 소스의 데이터를 표시할 때 데이터 소스의 스키마에 있는 열이 표시하려는 순서대로 나타나지 않는 경우가 있습니다.  <xref:System.Windows.Forms.DataGridViewColumn> 클래스의 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A> 속성을 사용하여 열의 표시 순서를 변경할 수 있습니다.  
  
 다음 코드 예제에서는 Northwind 샘플 데이터베이스의 Customers 테이블에 바인딩할 때 자동으로 생성되는 일부 열의 위치를 변경합니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤을 데이터베이스 테이블에 바인딩하는 방법에 대한 자세한 내용은 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)을 참조하세요.  
  
 Visual Studio에서는 이 작업이 지원됩니다.  [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에서 열 순서 변경](http://msdn.microsoft.com/library/hb1dk7ax\(v=vs.110\))  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#040)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#040](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#040)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스의 `Customers` 테이블과 같은 표시된 열 이름을 포함하는 테이블에 바인딩된 `customersDataGridView`라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName>, <xref:System.Data?displayProperty=fullName> 및 <xref:System.Xml?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 <xref:System.Windows.Forms.DataGridViewColumn.DisplayIndex%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에 데이터 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-data-to-the-windows-forms-datagridview-control.md)