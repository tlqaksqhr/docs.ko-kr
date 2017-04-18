---
title: "방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정 | Microsoft Docs"
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
  - "셀, 스타일 설정"
  - "데이터[Windows Forms], 형식 설정"
  - "데이터 형식"
  - "DataGridView 컨트롤[Windows Forms], 셀 스타일"
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# 방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정
<xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 전체 컨트롤, 특정 열, 행 및 열 머리글, 교대로 반복되는 행 등에 대해 기본 셀 스타일 및 셀 데이터 형식을 지정하여 장부 형식의 효과를 만들 수 있습니다.  열 및 교대로 반복되는 행에 대한 기본 스타일이 전체 컨트롤에 대한 기본 스타일 설정보다 우선적으로 적용되며  개별 행 및 열에 대해 코드에 설정한 스타일이 기본 스타일보다 우선적으로 적용됩니다.  
  
 셀 스타일에 대한 자세한 내용은 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)을 참조하십시오.  교대로 반복되는 행 스타일 설정에 대한 내용은 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)을 참조하십시오.  
  
 또한 컨트롤에 추가될 모든 행에 스타일을 적용하기 위해 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성을 사용하여 스타일을 설정할 수 있습니다.  행 템플릿에 대한 자세한 내용은 [방법: 행 템플릿을 사용하여 Windows Forms DataGridView 컨트롤에서 행 사용자 지정](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)을 참조하십시오.  
  
 다음 절차를 수행하려면 <xref:System.Windows.Forms.DataGridView> 컨트롤이 포함된 폼이 있는 **Windows 응용 프로그램** 프로젝트가 필요합니다.  이러한 프로젝트를 설정하는 데 대한 내용은 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)를 참조하십시오.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 컨트롤의 모든 셀에 기본 스타일을 설정하려면  
  
1.  디자이너에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 선택합니다.  
  
2.  **속성** 창에서 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭합니다.  **CellStyle 작성기** 대화 상자가 나타납니다.  
  
3.  속성을 설정하여 스타일을 정의하고 **미리 보기** 창을 사용하여 선택 내용을 확인합니다.  
  
> [!NOTE]
>  비주얼 스타일을 사용할 있는 경우 행 및 열 머리글\(<xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A> 제외\)의 스타일이 현재 테마에 의해 자동으로 지정됩니다. 이 경우 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 값은 무시됩니다.  
>   
>  디자이너를 사용하여 선택한 여러 <xref:System.Windows.Forms.DataGridView> 컨트롤에 대해 셀 스타일을 설정할 수 있지만, 해당 컨트롤이 사용자가 수정하려는 셀 스타일 속성에 대해 동일한 값을 갖고 있는 경우에만 가능합니다.  셀 스타일이 해당 속성에 대해 다르면 **CellStyle 작성기** 대화 상자의 **속성** 창이 비게 됩니다.  
  
### 개별 열에서 셀에 기본 스타일을 설정하려면  
  
1.  디자이너에서 <xref:System.Windows.Forms.DataGridView> 컨트롤을 마우스 오른쪽 단추로 클릭하고 **열 편집**을 선택합니다.  
  
2.  **선택한 열** 목록에서 열을 선택합니다.  
  
3.  **열 속성** 표에서 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭합니다.  **CellStyle 작성기** 대화 상자가 나타납니다.  
  
4.  속성을 설정하여 스타일을 정의하고 **미리 보기** 창을 사용하여 선택 내용을 확인합니다.  
  
### 셀 데이터의 형식을 지정하려면  
  
1.  위의 절차 중 하나를 사용하여 기본 셀 스타일 속성과 관련된 **CellStyle 작성기** 대화 상자를 표시합니다.  
  
2.  **CellStyle 작성기** 대화 상자에서 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성 옆에 있는 줄임표 단추\(![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\)를 클릭합니다.  **형식 문자열 대화 상자**가 나타납니다.  
  
3.  형식 유형을 선택한 다음 형식에 대한 세부 사항\(예: 표시할 소수 자릿수\)을 수정하고 **샘플** 상자를 사용하여 선택 내용을 확인합니다.  
  
4.  null 값이 포함될 가능성이 있는 데이터 소스에 <xref:System.Windows.Forms.DataGridView> 컨트롤을 바인딩하는 경우에는 **Null 값** 텍스트 상자에 입력합니다.  이 값은 셀 값이 null 참조\(Visual Basic의 경우 `Nothing`\)이거나 <xref:System.DBNull.Value?displayProperty=fullName>인 경우 표시됩니다.  
  
## 참고 항목  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=fullName>   
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/ko-kr/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)