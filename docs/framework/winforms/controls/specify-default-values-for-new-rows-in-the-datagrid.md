---
title: "방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정 | Microsoft Docs"
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
  - "데이터 표, 새 행의 기본값"
  - "DataGridView 컨트롤[Windows Forms], 데이터 입력"
  - "DataGridView 컨트롤[Windows Forms], 새 행의 기본값"
  - "행, 기본값 지정"
ms.assetid: 8d127963-d9f8-4e4e-9f7f-beb66688f1f2
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms DataGridView 컨트롤에서 새 행에 기본값 지정
응용 프로그램에서 새로 추가된 행을 기본값으로 채우면 보다 편리하게 데이터를 입력할 수 있습니다.  <xref:System.Windows.Forms.DataGridView> 클래스의 경우 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트를 사용하여 기본값을 채울 수 있습니다.  이 이벤트는 사용자가 새 레코드에 행을 입력하는 경우 발생됩니다.  코드에서 이 이벤트를 처리하면 원하는 셀을 선택한 값으로 채울 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> 이벤트를 사용하여 새 행에 기본값을 지정하는 방법을 보여 줍니다.  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#120)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#120)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   고유 `CustomerID` 값을 생성하는 `NewCustomerId` 함수  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤에서 새 레코드에 행 사용](../../../../docs/framework/winforms/controls/using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)