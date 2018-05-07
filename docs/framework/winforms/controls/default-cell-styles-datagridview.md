---
title: '방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정'
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 47e15afe71ed3497b634e965c96badcee2fe3ed4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 기본 셀 스타일 및 데이터 형식 설정
<xref:System.Windows.Forms.DataGridView> 제어를 사용 하면 기본 셀 스타일을 지정 하 고 셀 데이터 형식을 전체 컨트롤에 대 한, 특정 열에 대 한, 행 및 열 머리글에 대 한 대체 행 원장 효과를 만듭니다. 전체 컨트롤에 대해 설정 하는 기본 스타일은 기본적으로 열과 대체 행 스타일 설정 재정의 됩니다. 또한 개별 행 및 열에 대 한 코드에서 설정한 기본 스타일을 재정의 합니다.  
  
 셀 스타일에 대 한 자세한 내용은 참조 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)합니다. 교대로 반복 되는 행에 대 한 스타일을 설정 하려면 참조 [하는 방법:는 Windows Forms DataGridView 컨트롤 사용 하 여 디자이너에 교대로 반복 되는 행 스타일 설정](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)합니다.  
  
 사용 하 여 스타일을 설정할 수도 있습니다는 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> 속성을 컨트롤에 추가 될 모든 행에 영향을 줍니다. 행 템플릿에 대 한 자세한 내용은 참조 [하는 방법: Windows Forms DataGridView 컨트롤에서 사용자 지정 행을 행 템플릿을 사용](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)합니다.  
  
 다음 절차를 필요는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGridView> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>컨트롤의 모든 셀에 대 한 기본 스타일을 설정 하려면  
  
1.  선택 된 <xref:System.Windows.Forms.DataGridView> 디자이너에서 제어 합니다.  
  
2.  에 **속성** 창에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>, 또는 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성입니다. **CellStyle 작성기** 대화 상자가 나타납니다.  
  
3.  사용 하 여 속성을 설정 하 여 스타일을 정의 하는 **미리 보기** 선택 사항을 확인 하는 창입니다.  
  
> [!NOTE]
>  비주얼 스타일을 사용 하는 경우 행 및 열 머리글 (제외 하 고는 <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>)는 현재 테마에 따라 자동으로 스타일이 지정 재정의 <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> 및 <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> 속성 값입니다.  
>   
>  선택한 여러에 대 한 셀 스타일을 설정할 수 있습니다 <xref:System.Windows.Forms.DataGridView> 만 디자이너를 사용 하 여 수정 하려는 셀 스타일 속성에 대 한 동일한 값이 있는 경우를 제어 합니다. 해당 속성에 대 한 셀 스타일 다른 경우는 **속성** 의 창이 **CellStyle 작성기** 대화 상자가 비어 있게 됩니다.  
  
### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>개별 열에 기본 셀 스타일을 설정 하려면  
  
1.  마우스 오른쪽 단추로 클릭는 <xref:System.Windows.Forms.DataGridView> 디자이너에서 제어 하 고 선택 **열 편집**합니다.  
  
2.  열을 선택 된 **선택한 열** 목록입니다.  
  
3.  에 **열 속성** 그리드, 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> 속성입니다. **CellStyle 작성기** 대화 상자가 나타납니다.  
  
4.  사용 하 여 속성을 설정 하 여 스타일을 정의 하는 **미리 보기** 선택 사항을 확인 하는 창입니다.  
  
### <a name="to-format-data-in-cells"></a>셀의 데이터 서식을 지정 하려면  
  
1.  앞의 절차 중 하나를 사용 하 여 표시 하는 **CellStyle 작성기** 대화 상자에 기본 셀 스타일 속성이 관련이 있습니다.  
  
2.  에 **CellStyle 작성기** 대화 상자에서 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> 속성입니다. **형식 문자열** 대화 상자가 나타납니다.  
  
3.  형식 유형을 선택한 다음 형식 (예: 개수 표시 하려면 소수 자릿수)의 세부 정보를 수정를 사용 하는 **샘플** 선택 사항을 확인 하는 상자입니다.  
  
4.  바인딩하는 경우는 <xref:System.Windows.Forms.DataGridView> 컨트롤 입력, null 값을 포함할 가능성이 있는 데이터 소스는 **Null 값** 입력란. 이 값을 null 참조 셀 값이 같은 경우에 표시 됩니다 (`Nothing` Visual basic에서) 또는 <xref:System.DBNull.Value?displayProperty=nameWithType>합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>  
 [Windows Forms DataGridView 컨트롤의 셀 스타일](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [방법: 디자이너를 사용하여 Windows Forms DataGridView 컨트롤에 교대로 반복되는 행 스타일 설정](../../../../docs/framework/winforms/controls/set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
