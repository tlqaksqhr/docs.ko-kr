---
title: '방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 테이블 및 열 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 4b29a3040415cce8fad27abf9bf46aa3d3e14b4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528417"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤에 테이블 및 열 추가
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms에서 데이터를 표시할 수 있습니다 <xref:System.Windows.Forms.DataGrid> 컨트롤에 테이블과 열을 만들어서 <xref:System.Windows.Forms.DataGridTableStyle> 개체에 추가 하는 <xref:System.Windows.Forms.GridTableStylesCollection> 통해 액세스할 수 있는 개체는 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성입니다. 에 지정 된 모든 데이터 테이블의 내용을 표시 하는 각 테이블 스타일의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 의 속성은 <xref:System.Windows.Forms.DataGridTableStyle>합니다. 기본적으로 테이블 스타일 열 스타일을 지정 하지 않으면 해당 데이터 테이블 안의 모든 열 표시 됩니다. 추가 하 여 표시할 테이블에서 열을 제한할 수 있습니다 <xref:System.Windows.Forms.DataGridColumnStyle> 개체를 <xref:System.Windows.Forms.GridColumnStylesCollection>를 통해 액세스할는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 각 속성 <xref:System.Windows.Forms.DataGridTableStyle>합니다.  
  
 다음 절차를 필요는 **Windows 응용 프로그램** 포함 하는 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 이러한 프로젝트를 설정 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다. 기본적으로 [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> 내에 **도구 상자**합니다. 추가 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 도구 상자에 항목 추가](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>DataGrid 컨트롤 디자이너에 테이블을 추가 하려면  
  
1.  테이블의 데이터를 표시 하려면 먼저 바인딩해야는 <xref:System.Windows.Forms.DataGrid> 데이터 집합을 제어 합니다. 자세한 내용은 참조 [하는 방법: Windows Forms DataGrid 컨트롤을 데이터 원본 디자이너를 사용 하는 바인딩할](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)합니다.  
  
2.  선택 된 <xref:System.Windows.Forms.DataGrid> 컨트롤의 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성이 속성 창에서 줄임표 단추를 클릭 하 고 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 옆에 표시할 속성을는 **DataGridTableStyle 컬렉션 편집기**합니다.  
  
3.  컬렉션 편집기에서 클릭 **추가** 테이블 스타일을 삽입 합니다.  
  
4.  클릭 **확인** 컬렉션 편집기를 닫고를 닫은 다음 다시 옆에 있는 줄임표 단추를 클릭 하 여는 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성입니다.  
  
     컨트롤에 바인딩된 모든 데이터 테이블에 대 한 드롭다운 목록에 표시 됩니다 컬렉션 편집기를 다시 열 때는 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 테이블 스타일의 속성입니다.  
  
5.  에 **멤버** 상자 컬렉션 편집기의 테이블 스타일을 클릭 합니다.  
  
6.  에 **속성** 컬렉션 편집기 상자는 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 표시 하려는 테이블에 대 한 값입니다.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>디자이너의 DataGrid 컨트롤에 열을 추가 하려면  
  
1.  에 **멤버** 상자는 **DataGridTableStyle 컬렉션 편집기**, 해당 테이블 스타일을 선택 합니다. 에 **속성** 컬렉션 편집기 상자는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 컬렉션, 줄임표 단추를 클릭 하 고 (![VisualStudioEllipsesButton 스크린 샷] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) 표시 하 고 속성 옆에 **DataGridColumnStyle 컬렉션 편집기**합니다.  
  
2.  컬렉션 편집기에서 클릭 **추가** 열 스타일을 삽입 하거나 옆에 있는 아래쪽 화살표를 클릭 **추가** 열 형식을 지정할 수 있습니다.  
  
     드롭다운 목록 상자에서 선택할 수 있습니다는 <xref:System.Windows.Forms.DataGridTextBoxColumn> 또는 <xref:System.Windows.Forms.DataGridBoolColumn> 유형입니다.  
  
3.  확인을 눌러 닫습니다는 **DataGridColumnStyle 컬렉션 편집기**를 닫은 다음 옆에 있는 줄임표 단추를 클릭 하 여는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성입니다.  
  
     바인딩된 데이터 테이블에 있는 데이터 열에 대 한 드롭다운 목록에 표시 됩니다 컬렉션 편집기를 다시 열 때는 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 열 스타일의 속성입니다.  
  
4.  에 **멤버** 상자 컬렉션 편집기의 열 스타일을 클릭 합니다.  
  
5.  에 **속성** 컬렉션 편집기 상자는 <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> 표시 하려는 열에 대 한 값입니다.  
  
## <a name="see-also"></a>참고 항목  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
