---
title: "방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경 | Microsoft Docs"
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
  - "셀, DataGrid 셀 값 변경"
  - "DataGrid 컨트롤[Windows Forms], 데이터 바인딩"
  - "DataGrid 컨트롤[Windows Forms], 런타임에 동적으로 변경"
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  자세한 내용은 [Windows Forms DataGridView 컨트롤과 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 디자인 타임 기능을 사용하여 Windows Forms <xref:System.Windows.Forms.DataGrid>를 만든 후에는 런타임에 데이터 표에 있는 <xref:System.Data.DataSet> 개체의 요소를 동적으로 변경할 수 있습니다.  예를 들면 테이블의 개별 값을 변경하거나 <xref:System.Windows.Forms.DataGrid> 컨트롤에 바인딩된 데이터 소스를 변경할 수 있습니다.  테이블의 개별 값은 <xref:System.Windows.Forms.DataGrid> 컨트롤이 아니라 <xref:System.Data.DataSet> 개체를 통해 변경됩니다.  
  
### 프로그래밍 방식으로 데이터를 변경하려면  
  
1.  <xref:System.Data.DataSet> 개체에서 특정 테이블을 지정하고 이 테이블에서 행과 필드를 지정한 다음, 셀을 새 값과 같도록 설정합니다.  
  
    > [!NOTE]
    >  <xref:System.Data.DataSet>의 첫 번째 테이블 또는 테이블의 첫 번째 행을 지정하려면 0을 사용하십시오.  
  
     다음 예제에서는 `Button1`을 클릭하여 데이터 집합의 첫 번째 테이블에서 첫 번째 행의 두 번째 항목을 변경하는 방법을 보여 줍니다.  <xref:System.Data.DataSet>\(`ds`\) 및 테이블\(`0` 과 `1`\)은 이전에 만든 것입니다.  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     \([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\) 폼의 생성자에 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     런타임에 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 다른 데이터 소스에 바인딩할 수 있습니다.  예를 들어 각각 서로 다른 데이터베이스에 연결된 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 데이터 컨트롤이 여러 개 있을 수 있습니다.  
  
### 프로그래밍 방식으로 DataSource를 변경하려면  
  
1.  <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 바인딩할 데이터 소스 및 테이블의 이름으로 설정합니다.  
  
     다음 예제에서는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 사용하여 데이터 소스를 Pubs 데이터베이스의 Authors 테이블에 연결된 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 데이터 컨트롤\(adoPubsAuthors\)로 변경하는 방법을 보여 줍니다.  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## 참고 항목  
 [ADO.NET 데이터 집합](../../../../docs/framework/data/adonet/ado-net-datasets.md)   
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)   
 [방법: Windows Forms DataGrid 컨트롤에 테이블과 열 추가](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)   
 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)