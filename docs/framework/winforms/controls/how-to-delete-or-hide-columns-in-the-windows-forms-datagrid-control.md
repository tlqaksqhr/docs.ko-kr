---
title: "방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기 | Microsoft Docs"
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
  - "열[Windows Forms], 데이터 표에서 삭제"
  - "열[Windows Forms], 숨기기"
  - "데이터 표, 열 삭제"
  - "데이터 표, 열 숨기기"
  - "DataGrid 컨트롤[Windows Forms], 열 삭제"
  - "DataGrid 컨트롤[Windows Forms], 열 숨기기"
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 <xref:System.Windows.Forms.DataGridTableStyle> 클래스의 멤버인 <xref:System.Windows.Forms.GridColumnStylesCollection> 및 <xref:System.Windows.Forms.DataGridColumnStyle> 개체의 속성과 메서드를 사용하면 Windows Forms <xref:System.Windows.Forms.DataGrid> 컨트롤의 열을 프로그래밍 방식으로 삭제하거나 숨길 수 있습니다.  
  
 삭제되거나 숨겨진 열은 해당 데이터 표가 바인딩된 데이터 소스에 그대로 남아 있으므로 프로그래밍 방식으로 계속 액세스할 수 있습니다.  이러한 열은 데이터 표에 더 이상 나타나지 않을 뿐입니다.  
  
> [!NOTE]
>  응용 프로그램에서 액세스하지 않는 특정 데이터 열을 데이터 표에 표시하지 않으려면 데이터 소스에 해당 데이터 열을 포함할 필요가 없습니다.  
  
### 프로그래밍 방식으로 DataGrid에서 열을 삭제하려면  
  
1.  폼의 선언 영역에서 <xref:System.Windows.Forms.DataGridTableStyle> 클래스의 새 인스턴스를 선언합니다.  
  
2.  <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=fullName> 속성을 데이터 소스에서 스타일을 적용할 테이블로 설정합니다.  다음 예제에서는 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName> 속성을 이미 설정한 것으로 가정하여 사용합니다.  
  
3.  새 <xref:System.Windows.Forms.DataGridTableStyle> 개체를 데이터 표의 테이블 스타일 컬렉션에 추가합니다.  
  
4.  <xref:System.Windows.Forms.DataGrid>의 <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> 컬렉션에 대한 <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> 메서드를 호출합니다. 이 때 삭제할 열의 열 인덱스를 지정합니다.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### 프로그래밍 방식으로 DataGrid에서 열을 숨기려면  
  
1.  폼의 선언 영역에서 <xref:System.Windows.Forms.DataGridTableStyle> 클래스의 새 인스턴스를 선언합니다.  
  
2.  <xref:System.Windows.Forms.DataGridTableStyle>의 <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> 속성을 데이터 소스에서 스타일을 적용할 테이블로 설정합니다.  다음 코드 예제에서는 <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=fullName> 속성을 이미 설정한 것으로 가정하여 사용합니다.  
  
3.  새 <xref:System.Windows.Forms.DataGridTableStyle> 개체를 데이터 표의 테이블 스타일 컬렉션에 추가합니다.  
  
4.  설정 하 여 열을 숨기려면 해당`Width` 속성을 숨길 열의 열 인덱스를 지정 하는 0.  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## 참고 항목  
 [방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)   
 [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)