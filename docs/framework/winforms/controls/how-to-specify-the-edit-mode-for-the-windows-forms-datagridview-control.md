---
title: "방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정 | Microsoft Docs"
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
  - "데이터 표, 편집 모드"
  - "DataGridView 컨트롤[Windows Forms], 편집 모드"
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Forms DataGridView 컨트롤에 편집 모드 지정
기본적으로 사용자는 현재 <xref:System.Windows.Forms.DataGridView> 텍스트 상자 셀에서 직접 입력하거나 F2 키를 눌러 해당 텍스트 상자 셀의 내용을 편집할 수 있습니다.  이렇게 하면 다음 조건을 모두 만족하는 경우 셀이 편집 모드로 전환됩니다.  
  
-   내부 데이터 소스를 편집할 수 있는 경우  
  
-   <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용할 수 있는 경우  
  
-   <xref:System.Windows.Forms.DataGridView.EditMode%2A> 속성 값이 <xref:System.Windows.Forms.DataGridViewEditMode>가 아닌 경우  
  
-   셀, 행, 열 및 컨트롤의 `ReadOnly` 속성이 모두 `false`로 설정된 경우  
  
 편집 모드에서 사용자는 셀 값을 변경하고 Enter 키를 눌러 변경 내용을 커밋하거나 Esc 키를 눌러 셀을 원래 값으로 되돌릴 수 있습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤을 구성하여 셀이 현재 셀이 되는 즉시 편집 모드가 되도록 할 수 있습니다.  이 경우 Enter 키와 Esc 키의 동작은 변경되지 않지만 값을 커밋하거나 되돌린 후에도 셀이 편집 모드로 남아 있게 됩니다.  또한 해당 컨트롤을 구성하여 사용자가 셀에 입력하거나 F2 키를 누르는 경우 중 한 경우에만 셀이 편집 모드가 되도록 할 수 있습니다.  마지막으로 <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> 메서드를 호출하는 경우에만 셀이 편집 모드가 되도록 할 수도 있습니다.  
  
### DataGridView 컨트롤의 편집 모드를 변경하려면  
  
-   <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName> 속성을 적절한 <xref:System.Windows.Forms.DataGridViewEditMode> 열거형으로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System> 및 <xref:System.Windows.Forms> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 데이터 입력](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)