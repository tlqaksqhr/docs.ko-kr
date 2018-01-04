---
title: "방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경"
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
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c34c6207c29f008606cc4ace83aa4f94c41f6851
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a>방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경
> [!NOTE]
>  <xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다. 자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.  
  
 Windows Forms를 만든 후 <xref:System.Windows.Forms.DataGrid> 디자인 타임 기능을 사용 하 여 라면의 요소를 동적으로 변경 하는 <xref:System.Data.DataSet> 런타임 시 그리드 개체. 에 바인딩된 데이터 소스에 변경 또는 테이블의 개별 값에 대 한 변경 설명에 포함할 수는 <xref:System.Windows.Forms.DataGrid> 제어 합니다. 개별 값의 변경 내용을 통해 완료 되는 <xref:System.Data.DataSet> 개체가 아니라는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.  
  
### <a name="to-change-data-programmatically"></a>프로그래밍 방식으로 데이터를 변경 하려면  
  
1.  원하는 테이블 지정은 <xref:System.Data.DataSet> 개체 및 원하는 행 및 테이블에서 필드 및 셀 새 값으로 설정 합니다.  
  
    > [!NOTE]
    >  첫 번째 테이블을 지정 하는 <xref:System.Data.DataSet> 또는 테이블의 첫 번째 행 0을 사용 합니다.  
  
     다음 예제에서는 데이터 집합의 첫 번째 테이블의 첫 번째 행의 두 번째 항목을 클릭 하 여 변경 하는 방법을 보여 줍니다 `Button1`합니다. <xref:System.Data.DataSet> (`ds`) 및 테이블 (`0` 및 `1`)은 이전에 만든 합니다.  
  
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
  
     ([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 폼 생성자에 다음 코드를 추가하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     런타임 시 사용할 수 있습니다는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 바인딩하는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 다른 데이터 소스입니다. 예를 들어 여러 개 있을 수 있습니다 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 다른 데이터베이스에 연결 된 각 데이터 컨트롤입니다.  
  
### <a name="to-change-the-datasource-programmatically"></a>프로그래밍 방식으로 데이터 소스를 변경 하려면  
  
1.  설정의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 데이터 원본 및 바인딩할 하려는 테이블의 이름입니다.  
  
     사용 하 여 날짜 소스를 변경 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 프로그램 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Pubs 데이터베이스에서 Authors 테이블에 연결 되어 있는 데이터 제어 (adoPubsAuthors).  
  
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
  
## <a name="see-also"></a>참고 항목  
 [ADO.NET 데이터 집합](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
