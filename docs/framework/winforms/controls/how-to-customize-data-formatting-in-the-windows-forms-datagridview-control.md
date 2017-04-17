---
title: "방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정 | Microsoft Docs"
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
  - "셀, DataGridView 컨트롤에서 색 변경[Windows Forms]"
  - "색, DataGridView 컨트롤에서 변경[Windows Forms]"
  - "데이터[Windows Forms], DataGridView 컨트롤에서 형식 지정"
  - "데이터 표, 데이터 서식 지정"
  - "DataGridView 컨트롤[Windows Forms], 셀 사용자 지정"
  - "DataGridView 컨트롤[Windows Forms], 셀 스타일"
  - "DataGridView 컨트롤[Windows Forms], 셀 색상 변경"
  - "DataGridView 컨트롤[Windows Forms], 데이터 서식 지정"
  - "DataGridView 컨트롤[Windows Forms], 표시용 셀 값 대체"
  - "Windows Forms, DataGridView 셀의 색 변경"
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 방법: Windows Forms DataGridView 컨트롤에서 데이터 형식 사용자 지정
다음 코드 예제에서는 열과 값에 따라 셀이 표시되는 방식을 변경하는 <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName> 이벤트에 대한 처리기를 구현하는 방법을 보여 줍니다.  
  
 음수를 포함하는 `Balance` 열의 셀에는 빨간색 배경이 제공됩니다.  또한 이러한 셀에 통화 형식을 지정하여 음수 값을 괄호 안에 표시할 수도 있습니다.  자세한 내용은 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)을 참조하세요.  
  
 `Priority` 열의 셀에는 해당하는 텍스트 셀 값 대신 이미지가 표시됩니다.  <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs>의 <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> 속성은 텍스트 셀 값을 가져오고 해당하는 이미지 표시 값을 설정하는 데 사용됩니다.  
  
## 예제  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
-   실행 파일과 동일한 디렉터리에 있는 `highPri.bmp`, `mediumPri.bmp` 및 `lowPri.bmp`로 명명된 <xref:System.Drawing.Bitmap> 이미지  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Drawing.Bitmap>   
 [Windows Forms DataGridView 컨트롤에서 데이터 표시](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [방법: Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Windows Forms DataGridView 컨트롤의 데이터 형식 지정](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)