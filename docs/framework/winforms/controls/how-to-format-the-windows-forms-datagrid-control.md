---
title: "방법: Windows Forms DataGrid 컨트롤 서식 지정 | Microsoft Docs"
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
  - "색, DataGrid 컨트롤에 적용"
  - "열[Windows Forms], DataGrid 컨트롤"
  - "열[Windows Forms], DataGrid 컨트롤의 서식 지정"
  - "DataGrid 컨트롤[Windows Forms], 기본 스타일"
  - "DataGrid 컨트롤[Windows Forms], 서식 지정"
  - "서식 지정[Windows Forms]"
  - "테이블[Windows Forms], DataGrid 컨트롤의 서식 지정"
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms DataGrid 컨트롤 서식 지정
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGrid> 컨트롤의 여러 부분에 서로 다른 색을 적용하면 정보를 더 쉽게 읽고 해석할 수 있습니다.  행과 열에 색을 적용할 수 있으며  필요에 따라 행과 열을 숨기거나 표시할 수도 있습니다.  
  
 <xref:System.Windows.Forms.DataGrid> 컨트롤의 서식 지정과 관련된 세 가지 기본적인 사항이 있습니다.  속성을 설정하여 데이터가 표시되는 기본 스타일을 설정할 수 있습니다.  이를 기초로 특정 테이블이 런타임에 표시되는 방식을 사용자 지정할 수 있습니다.  마지막으로, 표시되는 색 및 기타 서식뿐 아니라 데이터 표에 표시할 열을 수정할 수 있습니다.  
  
 데이터 표의 서식을 지정하는 첫 단계로 <xref:System.Windows.Forms.DataGrid> 자체의 속성을 설정할 수 있습니다.  일단 색과 서식을 선택한 다음 이를 기초로 하여 표시되는 데이터 테이블과 열에 따라 변경 작업을 수행할 수 있습니다.  
  
### DataGrid 컨트롤에 대해 기본 스타일을 설정하려면  
  
1.  다음 속성을 적절하게 설정합니다.  
  
    |Property|설명|  
    |--------------|--------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A> 속성은 데이터 표에서 짝수 행의 색을 정의합니다.  <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 속성을 다른 색으로 설정하면 홀수 행\(1, 3, 5행 등\)에 해당 색이 적용됩니다.|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|데이터 표에서 짝수 행\(0, 2, 4, 6행 등\)의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<xref:System.Windows.Forms.DataGrid.BackColor%2A> 및 <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> 속성은 데이터 표에서 행의 색을 지정하지만 <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> 속성은 데이터 표를 아래로 스크롤하거나 데이터 표에 행이 많지 않을 때만 보이는 행 이외 영역의 색을 지정합니다.|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|데이터 표의 테두리 스타일이며 <xref:System.Windows.Forms.BorderStyle> 열거형 값 중 하나입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|데이터 표 바로 위에 표시되는 데이터 표 창 캡션의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|데이터 표 위쪽에 있는 캡션의 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|데이터 표 창 캡션의 배경색입니다.|  
    |<xref:System.Windows.Forms.Control.Font%2A>|데이터 표에서 텍스트를 표시하는 데 사용되는 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|데이터 표의 행에서 데이터가 표시되는 글꼴의 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|데이터 표에서 모눈선의 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|데이터 표의 각 셀을 구분하는 선의 스타일이며 <xref:System.Windows.Forms.DataGridLineStyle> 열거형 값 중 하나입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|행 및 열 머리글의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|열 머리글에 사용되는 글꼴입니다.|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|데이터 표 열 머리글의 전경색입니다. 여기에는 열 머리글 텍스트와 여러 관련 테이블이 표시될 때 행을 확장하기 위한 \+\/\- 문자 모양이 포함됩니다.|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|데이터 표에 있는 자식 테이블, 관계 이름 등에 대한 링크를 비롯한 모든 링크의 텍스트 색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|자식 테이블에서 이 속성은 부모 행의 배경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|자식 테이블에서 이 속성은 부모 행의 전경색입니다.|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|테이블 및 열 이름이 <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> 열거형을 통해 부모 행에 표시되는지 여부를 결정합니다.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|데이터 표에서 열의 기본 너비\(픽셀\)입니다.  개별적으로 또는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 통해 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 다시 설정하기 전에 이 속성을 설정합니다. 그렇지 않으면 이 속성을 설정해도 효과가 없습니다.<br /><br /> 이 속성의 값은 0 이상이어야 합니다.|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|데이터 표에서 행의 높이\(픽셀\)입니다.  개별적으로 또는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 통해 <xref:System.Windows.Forms.DataGrid.DataSource%2A> 및 <xref:System.Windows.Forms.DataGrid.DataMember%2A> 속성을 다시 설정하기 전에 이 속성을 설정합니다. 그렇지 않으면 이 속성을 설정해도 효과가 없습니다.<br /><br /> 이 속성의 값은 0 이상이어야 합니다.|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|데이터 표에서 행 머리글의 너비입니다.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|행이나 셀을 선택하면 이 속성이 배경색이 됩니다.|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|행이나 셀을 선택하면 이 속성이 전경색이 됩니다.|  
  
    > [!NOTE]
    >  컨트롤의 색을 사용자 지정할 때 색을 부적절하게 선택\(예: 빨강 및 녹색\)하면 컨트롤에 액세스할 수 없게 됩니다.  이러한 문제를 방지하려면 **시스템 색** 색상표에 있는 색을 사용합니다.  
  
     다음 절차에서는 데이터 테이블에 바인딩된 <xref:System.Windows.Forms.DataGrid> 컨트롤이 폼에 있다고 가정합니다.  자세한 내용은 [Windows Forms DataGrid 컨트롤을 데이터 소스에 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)을 참조하십시오.  
  
### 프로그래밍 방식으로 데이터 테이블의 테이블 및 열 스타일을 설정하려면  
  
1.  새 테이블 스타일을 만들고 속성을 설정합니다.  
  
2.  열 스타일을 만들고 속성을 설정합니다.  
  
3.  만든 열 스타일을 테이블 스타일의 열 스타일 컬렉션에 추가합니다.  
  
4.  만든 테이블 스타일을 데이터 표의 테이블 스타일 컬렉션에 추가합니다.  
  
5.  아래 예제에서는 새 <xref:System.Windows.Forms.DataGridTableStyle>의 인스턴스를 만들고 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성을 설정합니다.  
  
6.  **GridColumnStyle**의 새 인스턴스를 만들고, **MappingName**을 설정하고, 기타 레이아웃 및 표시 속성을 설정합니다.  
  
7.  만들려는 각 열 스타일에 대해 2단계에서 6단계까지를 반복합니다.  
  
     다음 예제에서는 열 안에 이름을 표시하기 위해 <xref:System.Windows.Forms.DataGridTextBoxColumn>을 만드는 방법을 보여 줍니다.  또한 열 스타일을 테이블 스타일의 <xref:System.Windows.Forms.GridColumnStylesCollection>에 추가하고 테이블 스타일을 데이터 표의 <xref:System.Windows.Forms.GridTableStylesCollection>에 추가합니다.  
  
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
  
## 참고 항목  
 <xref:System.Windows.Forms.GridTableStylesCollection>   
 <xref:System.Windows.Forms.GridColumnStylesCollection>   
 <xref:System.Windows.Forms.DataGrid>   
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [DataGrid 컨트롤](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)