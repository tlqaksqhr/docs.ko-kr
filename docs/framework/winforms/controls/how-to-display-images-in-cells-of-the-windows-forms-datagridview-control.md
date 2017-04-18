---
title: "방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시 | Microsoft Docs"
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
  - "셀, 이미지 표시"
  - "데이터 표, 셀에 이미지 표시"
  - "데이터 표, 표에 표시"
  - "DataGridView 컨트롤[Windows Forms], 이미지 표시"
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms DataGridView 컨트롤의 셀에 이미지 표시
그림이나 그래픽은 데이터 행에 표시할 수 있는 값 중 하나입니다.  이러한 그래픽은 직원 사진이나 회사 로고 형식인 경우가 많습니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤에 데이터를 표시하면 그림이 간단하게 통합됩니다.  <xref:System.Windows.Forms.DataGridView> 컨트롤은 일부 데이터베이스에서 사용되는 OLE 그림 형식뿐만 아니라 <xref:System.Drawing.Image> 클래스에서 지원하는 모든 이미지 형식을 기본적으로 처리합니다.  
  
 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터 소스에 이미지 열이 있는 경우 <xref:System.Windows.Forms.DataGridView> 컨트롤에 의해 해당 이미지 열이 자동으로 표시됩니다.  
  
 다음 코드 예제에서는 포함 리소스에서 아이콘을 추출한 다음 비트맵으로 변환하여 이미지 열의 모든 셀에 표시하는 방법을 보여 줍니다.  텍스트 셀 값을 해당 이미지로 바꾸는 다른 예제를 보려면 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   이름이 `dataGridView1`인 <xref:System.Windows.Forms.DataGridView> 컨트롤  
  
-   `tree.ico`라는 포함 아이콘 리소스  
  
-   <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> 및 <xref:System.Drawing?displayProperty=fullName> 어셈블리에 대한 참조  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 [Windows Forms DataGridView 컨트롤의 기본 열, 행 및 셀 기능](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)