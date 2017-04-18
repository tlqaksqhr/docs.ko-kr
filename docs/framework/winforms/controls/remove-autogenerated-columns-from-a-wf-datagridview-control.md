---
title: "방법: 자동으로 생성된 열을 Windows Forms DataGridView 컨트롤에서 제거 | Microsoft Docs"
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
  - "열[Windows Forms], 제거"
  - "DataGridView 컨트롤[Windows Forms], 열 제거"
ms.assetid: 92e28d98-95a3-446c-9150-41b7c7e5be15
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 자동으로 생성된 열을 Windows Forms DataGridView 컨트롤에서 제거
<xref:System.Windows.Forms.DataGridView> 컨트롤이 해당 데이터 소스의 데이터를 기반으로 해당 열을 자동으로 생성하도록 설정된 경우 필요에 따라 특정 열을 생략할 수 있습니다.  <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션의 <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> 메서드를 호출하여 이 작업을 수행할 수 있습니다.  또는 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `false`로 설정하여 뷰에서 열을 숨길 수 있습니다.  이러한 기술은 특정 조건에서 숨겨진 열을 표시하거나 열을 표시하지 않고 열의 데이터에 액세스해야 하는 경우 유용합니다.  
  
### 자동으로 생성된 열을 제거하려면  
  
-   <xref:System.Windows.Forms.DataGridView.Columns%2A> 컬렉션의 <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A> 메서드를 호출합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#111)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#111)]  
  
### 자동으로 생성된 열을 숨기려면  
  
-   열의 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> 속성을 `false`로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#112)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#112](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#112)]  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#110)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#110)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   Northwind 샘플 데이터베이스에 있는 `Customers` 테이블과 같이 `Fax` 및 `CustomerID` 열을 포함하는 테이블에 바인딩된 `dataGridView1`이라는 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumnCollection.Remove%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)