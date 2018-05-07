---
title: '방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤 서식 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: c6069c2557ac220a37db7f16917a029d6fa49522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>방법: 디자이너를 사용하여 Windows Forms DataGrid 컨트롤 서식 지정
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 다양 한 부분에 다른 색상을 적용 한 <xref:System.Windows.Forms.DataGrid> 컨트롤에 정보를 더 쉽게 읽고 해석 하기를 높일 수 있습니다. 행 및 열에 색을 적용할 수 있습니다. 행과 열 수 또한 숨겨지거나 표시 되려고 판단에 따라 합니다.  
  
 다음 세 가지 기본 측면 서식 지정은 <xref:System.Windows.Forms.DataGrid> 제어:  
  
-   데이터 표시 되는 기본 스타일을 설정 하는 속성을 설정할 수 있습니다.  
  
-   그런 다음 해당 자료에서 특정 테이블이 런타임 시 표시 되는 방식을 사용자 지정할 수 있습니다.  
  
-   마지막으로, 색 뿐만 아니라 데이터 표에 표시 된 열을 수정할 수 있습니다 하 고 기타 서식 표시 됩니다.  
  
 데이터 표 서식 지정에 첫 단계로 속성을 설정할 수 있습니다는 <xref:System.Windows.Forms.DataGrid> 자체입니다. 이러한 색과 서식을 선택한을 변경할 수 있습니다 다음 데이터 테이블 및 표시 되는 열에 따라 기본을 형성 합니다.  
  
 다음 절차를 수행 하려면는 **Windows 응용 프로그램** 포함 된 폼을 사용 하 여 프로젝트는 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 이러한 프로젝트 설정에 대 한 정보를 참조 하십시오. [하는 방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) 및 [하는 방법: Windows Forms에 컨트롤 추가](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)합니다. [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> 내에 **도구 상자** 기본적으로 합니다. 자세한 내용은 참조 [하는 방법: 도구 상자에 항목 추가](http://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>DataGrid 컨트롤에 대 한 기본 스타일을 설정 하려면  
  
1.  <xref:System.Windows.Forms.DataGrid> 컨트롤을 선택합니다.  
  
2.  에 **속성** 창을 적절 하 게 다음 속성을 설정 합니다.  
  
    |속성|설명|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|`BackColor` 속성 표에 있는 짝수 번호 행의 색을 정의 합니다. 설정 하는 경우는 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 속성을 다른 색으로 다른 모든 행은 색이 설정 되어 (행에 1, 3, 5, 및 등).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|표에 있는 짝수 번호 행의 배경색 (행에 0, 2, 4, 6, 및 등).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|반면는 <xref:System.Windows.Forms.DataGrid.BackColor%2A> 및 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 표의 행 색을 결정 하는 속성의 <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> 모눈을 아래로 스크롤할 또는 경우에 행을 몇 개 에서만 볼 수 있는 행 영역 외부의 영역 색을 결정 하는 속성 모눈에 포함 합니다.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|눈금의 테두리 스타일 중 하나는 <xref:System.Windows.Forms.BorderStyle> 열거형 값입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|바로 모눈 위에 표시 되는 데이터 표 창 캡션의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|눈금의 위쪽 캡션의 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|표 창 캡션의 배경색입니다.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|눈금에서 텍스트를 표시 하는 데 사용 되는 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|데이터 표 행의 데이터에 의해 표시 되는 글꼴의 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|데이터 표의 모눈선의 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|중 하나는 눈금의 셀을 구분 하는 선의 스타일은 <xref:System.Windows.Forms.DataGridLineStyle> 열거형 값입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|행 및 열 머리글의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|열 머리글에 사용 되는 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|열 머리글 텍스트 더하기 기호 (+) 및 빼기 기호 (-)는 여러 관련 테이블 행을 축소 및 확장의 문자를 포함 하 여 표의 열 머리글의 전경색 표시 됩니다.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|자식 테이블, 관계 이름 등에 대 한 링크를 포함 하 여 데이터 표의 모든 링크의 텍스트의 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|자식 테이블에서 부모 행의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|자식 테이블에서 부모 행의 전경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|방법으로 테이블 및 열 이름을 부모 행에 표시 되는지 여부를 결정은 <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> 열거형입니다.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|데이터 표에서 열의 기본 너비(픽셀)입니다. 다시 설정 하기 전에이 속성을 설정 합니다.는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성 (중 하나 별도로 또는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드), 또는 속성이 아무런 효과가 없습니다.<br /><br /> 속성은 0 보다 작은 값으로 설정할 수 없습니다.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|행의 높이 (픽셀 단위) 표의 행입니다. 다시 설정 하기 전에이 속성을 설정 합니다.는 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성 (중 하나 별도로 또는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드), 또는 속성이 아무런 효과가 없습니다.<br /><br /> 속성은 0 보다 작은 값으로 설정할 수 없습니다.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|모눈의 행 머리글의 너비입니다.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|행 또는 셀을 선택 하면 이것이 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|행 또는 셀을 선택 하면 이것이 전경색입니다.|  
  
    > [!NOTE]
    >  컨트롤의 색 사용자 지정 하는 경우에 컨트롤을 저하 색 선택을 (예를 들어 빨간색 및 녹색)에 액세스할 수 없게 만들 수 있습니다. 사용할 수 있는 색을 사용 하 여는 **시스템 색** 이 문제를 피하려면 색상표입니다.  
  
     다음 절차를 수행 하려면는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 데이터 테이블에 연결 합니다. 자세한 내용은 참조 [하는 방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)합니다.  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>디자인 타임에 데이터 테이블의 테이블 및 열 스타일을 설정 하려면  
  
1.  선택 된 <xref:System.Windows.Forms.DataGrid> 폼의 컨트롤로 합니다.  
  
2.  에 **속성** 창의 선택 된 <xref:System.Windows.Forms.DataGrid.TableStyles%2A> 속성을 클릭은 **줄임표** (![VisualStudioEllipsesButton 스크린 샷] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) 단추입니다.  
  
3.  에 **DataGridTableStyle 컬렉션 편집기** 대화 상자를 클릭 **추가** 테이블 스타일 컬렉션에 추가 하려면.  
  
     와 **DataGridTableStyle 컬렉션 편집기**, 추가할 수 있습니다 및 매핑 테이블 스타일에 대 한 이름을 제거 테이블 스타일과 디스플레이 설정 및 레이아웃 속성을 설정 합니다.  
  
4.  설정의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성을 각 테이블 스타일에 대 한 매핑 이름입니다.  
  
     어떤 테이블에 테이블 스타일을 사용 해야 지정할 매핑 이름이 사용 됩니다.  
  
5.  에 **DataGridTableStyle 컬렉션 편집기**, 선택는 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 속성 줄임표 단추를 클릭 하 고 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton ")).  
  
6.  에 **DataGridColumnStyle 컬렉션 편집기** 대화 상자에서 만든 테이블 스타일을 열 스타일을 추가 합니다.  
  
     와 **DataGridColumnStyle 컬렉션 편집기**형식 지정 문자열 데이터에 대 한 열을 추가 하 고 열 스타일을 제거, 표시 및 레이아웃 속성을 설정 하 고 설정할 수는 매핑 이름입니다.  
  
    > [!NOTE]
    >  문자열 형식 지정 하는 방법에 대 한 자세한 내용은 참조 [형식 지정](../../../../docs/standard/base-types/formatting-types.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
