---
title: "방법: Windows Forms DataGridView 컨트롤에서 현재 셀 가져오기 및 설정 | Microsoft Docs"
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
  - "셀, 현재 셀 가져오기 및 설정"
  - "DataGridView 컨트롤[Windows Forms], 현재 셀 가져오기"
  - "DataGridView 컨트롤[Windows Forms], 현재 셀 설정"
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms DataGridView 컨트롤에서 현재 셀 가져오기 및 설정
<xref:System.Windows.Forms.DataGridView>와 상호 작용하려면 현재 활성화된 셀을 프로그래밍 방식으로 검색해야 하는 경우가 많습니다.  또한 현재 셀을 변경해야 할 수 있습니다.  <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성을 사용하여 이러한 작업을 수행할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> 속성이 `false`로 설정된 행이나 열에서는 현재 셀을 설정할 수 없습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 선택 모드에 따라 현재 셀을 변경하면 선택 내용이 변경될 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤의 선택 모드](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)를 참조하십시오.  
  
### 현재 셀을 프로그래밍 방식으로 가져오려면  
  
-   <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성을 사용합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### 현재 셀을 프로그래밍 방식으로 설정하려면  
  
-   <xref:System.Windows.Forms.DataGridView> 컨트롤의 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> 속성을 설정합니다.  다음 코드 예제에서는 현재 셀을 행 0, 열 1로 설정합니다.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   `getCurrentCellButton` 및 `setCurrentCellButton`이라는 <xref:System.Windows.Forms.Button> 컨트롤.  [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 경우 각 단추에 대한 <xref:System.Windows.Forms.Control.Click> 이벤트를 예제 코드의 관련 이벤트 처리기에 연결해야 합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   <xref:System?displayProperty=fullName> 및 <xref:System.Windows.Forms?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 선택 모드](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)