---
title: '방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: 1059f774ae8d2c203d7a4f5c02c597b4686304f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526916"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="eeda1-102">방법: 런타임에 Windows Forms DataGrid 컨트롤에 표시되는 데이터 변경</span><span class="sxs-lookup"><span data-stu-id="eeda1-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="eeda1-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="eeda1-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eeda1-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="eeda1-105">Windows Forms를 만든 후 <xref:System.Windows.Forms.DataGrid> 디자인 타임 기능을 사용 하 여 라면의 요소를 동적으로 변경 하는 <xref:System.Data.DataSet> 런타임 시 그리드 개체.</span><span class="sxs-lookup"><span data-stu-id="eeda1-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="eeda1-106">에 바인딩된 데이터 소스에 변경 또는 테이블의 개별 값에 대 한 변경 설명에 포함할 수는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="eeda1-107">개별 값의 변경 내용을 통해 완료 되는 <xref:System.Data.DataSet> 개체가 아니라는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="eeda1-108">프로그래밍 방식으로 데이터를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="eeda1-108">To change data programmatically</span></span>  
  
1.  <span data-ttu-id="eeda1-109">원하는 테이블 지정은 <xref:System.Data.DataSet> 개체 및 원하는 행 및 테이블에서 필드 및 셀 새 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="eeda1-110">첫 번째 테이블을 지정 하는 <xref:System.Data.DataSet> 또는 테이블의 첫 번째 행 0을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="eeda1-111">다음 예제에서는 데이터 집합의 첫 번째 테이블의 첫 번째 행의 두 번째 항목을 클릭 하 여 변경 하는 방법을 보여 줍니다 `Button1`합니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="eeda1-112"><xref:System.Data.DataSet> (`ds`) 및 테이블 (`0` 및 `1`)은 이전에 만든 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="eeda1-113">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-113">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="eeda1-114">런타임 시 사용할 수 있습니다는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 바인딩하는 <xref:System.Windows.Forms.DataGrid> 컨트롤을 다른 데이터 소스입니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="eeda1-115">예를 들어 여러 개 있을 수 있습니다 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 다른 데이터베이스에 연결 된 각 데이터 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-115">For example, you may have several [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="eeda1-116">프로그래밍 방식으로 데이터 소스를 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="eeda1-116">To change the DataSource programmatically</span></span>  
  
1.  <span data-ttu-id="eeda1-117">설정의 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 데이터 원본 및 바인딩할 하려는 테이블의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="eeda1-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="eeda1-118">사용 하 여 날짜 소스를 변경 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> 메서드를 프로그램 [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Pubs 데이터베이스에서 Authors 테이블에 연결 되어 있는 데이터 제어 (adoPubsAuthors).</span><span class="sxs-lookup"><span data-stu-id="eeda1-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eeda1-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eeda1-119">See Also</span></span>  
 [<span data-ttu-id="eeda1-120">ADO.NET 데이터 집합</span><span class="sxs-lookup"><span data-stu-id="eeda1-120">ADO.NET DataSets</span></span>](../../../../docs/framework/data/adonet/ado-net-datasets.md)  
 [<span data-ttu-id="eeda1-121">방법: Windows Forms DataGrid 컨트롤에서 열 삭제 또는 숨기기</span><span class="sxs-lookup"><span data-stu-id="eeda1-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="eeda1-122">방법: Windows Forms DataGrid 컨트롤에 테이블 및 열 추가</span><span class="sxs-lookup"><span data-stu-id="eeda1-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="eeda1-123">방법: 데이터 소스에 Windows Forms DataGrid 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="eeda1-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
