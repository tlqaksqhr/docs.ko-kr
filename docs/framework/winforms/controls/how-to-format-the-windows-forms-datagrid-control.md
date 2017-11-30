---
title: "방법: Windows Forms DataGrid 컨트롤 서식 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8518fdcaca7ebed65d0923b9bc1fe1a6797b97c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a>방법: Windows Forms DataGrid 컨트롤 서식 지정
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 다양 한 부분에 다른 색상을 적용 한 <xref:System.Windows.Forms.DataGrid> 컨트롤에 정보를 더 쉽게 읽고 해석 하기를 높일 수 있습니다. 행 및 열에 색을 적용할 수 있습니다. 행과 열 수 또한 숨겨지거나 표시 되려고 판단에 따라 합니다.  
  
 다음 세 가지 기본 측면 서식 지정은 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 데이터 표시 되는 기본 스타일을 설정 하는 속성을 설정할 수 있습니다. 그런 다음 해당 자료에서 특정 테이블이 런타임 시 표시 되는 방식을 사용자 지정할 수 있습니다. 마지막으로, 색 뿐만 아니라 데이터 표에 표시 된 열을 수정할 수 있습니다 하 고 기타 서식 표시 됩니다.  
  
 데이터 표 서식 지정에 첫 단계로 속성을 설정할 수 있습니다는 <xref:System.Windows.Forms.DataGrid> 자체입니다. 이러한 색과 서식을 선택한을 변경할 수 있습니다 다음 데이터 테이블 및 표시 되는 열에 따라 기본을 형성 합니다.  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>DataGrid 컨트롤에 대 한 기본 스타일을 설정 하려면  
  
1.  다음 속성을 적절 하 게 설정:  
  
    |속성|설명|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A> 속성 표에 있는 짝수 번호 행의 색을 정의 합니다. 설정 하는 경우는 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 속성을 다른 색으로 다른 모든 행은 색이 설정 되어 (행에 1, 3, 5, 및 등).|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|표에 있는 짝수 번호 행의 배경색 (행에 0, 2, 4, 6, 및 등).|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|반면는 <xref:System.Windows.Forms.DataGrid.BackColor%2A> 및 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 표의 행 색을 결정 하는 속성의 <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> 모눈을 아래로 스크롤할 또는에 포함 된 몇 가지 행만 볼 수만 인 이외 영역의 색을 결정 하는 속성 표입니다.|  
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
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|열 머리글 텍스트 및 + /-문자 모양이 (여러 개의 관련된 테이블 표시 되는 행을 확장)를 포함 하 여 표의 열 머리글의 전경색입니다.|  
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
    >  컨트롤에 액세스할 수 없게 합니다 (예를 들어 빨간색 및 녹색) 저하 색 선택을 시킬 수 있다는 것 컨트롤의 색을 사용자 지정할 때을 염두에 둬야 합니다. 사용할 수 있는 색을 사용 하 여는 **시스템 색** 이 문제를 피하려면 색상표입니다.  
  
     다음 절차에서는 폼에는 <xref:System.Windows.Forms.DataGrid> 컨트롤이 데이터 테이블에 연결 합니다. 자세한 내용은 참조 [데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)합니다.  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a>데이터 테이블의 테이블 및 열 스타일을 프로그래밍 방식으로 설정 하려면  
  
1.  새 테이블 스타일을 만들고 해당 속성을 설정 합니다.  
  
2.  열 스타일을 만들고 해당 속성을 설정 합니다.  
  
3.  테이블 스타일의 열 스타일 컬렉션에 열 스타일을 추가 합니다.  
  
4.  데이터 표 테이블 스타일 컬렉션에 테이블 스타일을 추가 합니다.  
  
5.  아래 예제에서는 새 인스턴스를 만들고 <xref:System.Windows.Forms.DataGridTableStyle> 설정 하 고 해당 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성입니다.  
  
6.  새 인스턴스를 만들고는 **GridColumnStyle** 설정 하 고 해당 **MappingName** (및 일부 다른 레이아웃 및 디스플레이 속성).  
  
7.  만들려는 각 열의 스타일에 대해 2 ~ 6 단계를 반복 합니다.  
  
     다음 예제에서는 어떻게는 <xref:System.Windows.Forms.DataGridTextBoxColumn> 열에 표시 되는 이름은 이므로 만들어집니다. 열 스타일을 추가 하는 또한는 <xref:System.Windows.Forms.GridColumnStylesCollection> 테이블 스타일의 테이블 스타일을 추가 하 고는 <xref:System.Windows.Forms.GridTableStylesCollection> 데이터 표의 합니다.  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.GridTableStylesCollection>  
 <xref:System.Windows.Forms.GridColumnStylesCollection>  
 <xref:System.Windows.Forms.DataGrid>  
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
