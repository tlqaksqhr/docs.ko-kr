---
title: "방법: Windows Forms DataGrid 컨트롤을 사용하여 입력 유효성 검사"
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
helpviewer_keywords:
- DataGrid control [Windows Forms], examples
- user input [Windows Forms], validating
- examples [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], validating input
- validation [Windows Forms], user input
ms.assetid: f1e9c3a0-d0a1-4893-a615-b4b0db046c63
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 88cdc7914c301af0f0f244f935b986fb78ec775e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-validate-input-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="a966d-102">방법: Windows Forms DataGrid 컨트롤을 사용하여 입력 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="a966d-102">How to: Validate Input with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="a966d-103"><xref:System.Windows.Forms.DataGridView> 컨트롤은 <xref:System.Windows.Forms.DataGrid> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.DataGrid> 컨트롤을 계속 유지하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a966d-104">자세한 내용은 [Windows Forms DataGridView 및 DataGrid 컨트롤의 차이점](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a966d-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="a966d-105">Windows Forms에 사용할 수 있는 두 가지 유형의 입력된 유효성 검사는 <xref:System.Windows.Forms.DataGrid> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-105">There are two types of input validation available for the Windows Forms <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="a966d-106">사용자가을 정수에 문자열을 예를 들어 셀에 대 한 허용 되지 않는 데이터 형식의 값을 입력 하는 경우 잘못 된 값 이전 값으로 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-106">If the user attempts to enter a value that is of an unacceptable data type for the cell, for example a string into an integer, the new invalid value is replaced with the old value.</span></span> <span data-ttu-id="a966d-107">이러한 종류의 입력된 유효성 검사 동작은 자동으로 수행 하 고 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-107">This kind of input validation is done automatically and cannot be customized.</span></span>  
  
 <span data-ttu-id="a966d-108">맞지 않는 데이터를 1 또는 부적절 한 문자열 보다 크거나 해야 하는 필드의 예를 들어 0 값을 거부 하도록 다른 유형의 입력된 유효성 검사를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-108">The other type of input validation can be used to reject any unacceptable data, for example a 0 value in a field that must be greater than or equal to 1, or an inappropriate string.</span></span> <span data-ttu-id="a966d-109">에 대 한 이벤트 처리기를 작성 하 여 데이터 집합에 이렇게는 <xref:System.Data.DataTable.ColumnChanging> 또는 <xref:System.Data.DataTable.RowChanging> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-109">This is done in the dataset by writing an event handler for the <xref:System.Data.DataTable.ColumnChanging> or <xref:System.Data.DataTable.RowChanging> event.</span></span> <span data-ttu-id="a966d-110">사용 하 여 다음 예제에서는 <xref:System.Data.DataTable.ColumnChanging> 이벤트 사용할 수 없는 값이 허용 되지 않습니다 "Product" 열에 대 한 특히 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-110">The example below uses the <xref:System.Data.DataTable.ColumnChanging> event because the unacceptable value is disallowed for the "Product" column in particular.</span></span> <span data-ttu-id="a966d-111">사용할 수는 <xref:System.Data.DataTable.RowChanging> "종료 날짜" 열의 값이 동일한 행에 있는 "" 시작 날짜 열 보다 늦습니다 검사에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-111">You might use the <xref:System.Data.DataTable.RowChanging> event for checking that the value of an "End Date" column is later than the "Start Date" column in the same row.</span></span>  
  
### <a name="to-validate-user-input"></a><span data-ttu-id="a966d-112">사용자 입력의 유효성을 검사 하려면</span><span class="sxs-lookup"><span data-stu-id="a966d-112">To validate user input</span></span>  
  
1.  <span data-ttu-id="a966d-113">처리할 코드를 작성은 <xref:System.Data.DataTable.ColumnChanging> 적절 한 테이블에 대 한 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-113">Write code to handle the <xref:System.Data.DataTable.ColumnChanging> event for the appropriate table.</span></span> <span data-ttu-id="a966d-114">부적절 한 입력 감지 되 면 호출 된 <xref:System.Data.DataRow.SetColumnError%2A> 의 메서드는 <xref:System.Data.DataRow> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-114">When inappropriate input is detected, call the <xref:System.Data.DataRow.SetColumnError%2A> method of the <xref:System.Data.DataRow> object.</span></span>  
  
    ```vb  
    Private Sub Customers_ColumnChanging(ByVal sender As Object, _  
    ByVal e As System.Data.DataColumnChangeEventArgs)  
       ' Only check for errors in the Product column  
       If (e.Column.ColumnName.Equals("Product")) Then  
          ' Do not allow "Automobile" as a product.  
          If CType(e.ProposedValue, String) = "Automobile" Then  
             Dim badValue As Object = e.ProposedValue  
             e.ProposedValue = "Bad Data"  
             e.Row.RowError = "The Product column contians an error"  
             e.Row.SetColumnError(e.Column, "Product cannot be " & _  
             CType(badValue, String))  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    //Handle column changing events on the Customers table  
    private void Customers_ColumnChanging(object sender, System.Data.DataColumnChangeEventArgs e) {  
  
       //Only check for errors in the Product column  
       if (e.Column.ColumnName.Equals("Product")) {  
  
          //Do not allow "Automobile" as a product  
          if (e.ProposedValue.Equals("Automobile")) {  
             object badValue = e.ProposedValue;  
             e.ProposedValue = "Bad Data";  
             e.Row.RowError = "The Product column contains an error";  
             e.Row.SetColumnError(e.Column, "Product cannot be " + badValue);  
          }  
       }  
    }  
    ```  
  
2.  <span data-ttu-id="a966d-115">이벤트에 이벤트 처리기를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-115">Connect the event handler to the event.</span></span>  
  
     <span data-ttu-id="a966d-116">다음 전체 코드는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트 또는 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="a966d-116">Place the following code within either the form's <xref:System.Windows.Forms.Form.Load> event or its constructor.</span></span>  
  
    ```vb  
    ' Assumes the grid is bound to a dataset called customersDataSet1  
    ' with a table called Customers.  
    ' Put this code in the form's Load event or its constructor.  
    AddHandler customersDataSet1.Tables("Customers").ColumnChanging, AddressOf Customers_ColumnChanging  
    ```  
  
    ```csharp  
    // Assumes the grid is bound to a dataset called customersDataSet1  
    // with a table called Customers.  
    // Put this code in the form's Load event or its constructor.  
    customersDataSet1.Tables["Customers"].ColumnChanging += new DataColumnChangeEventHandler(this.Customers_ColumnChanging);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a966d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a966d-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Data.DataTable.ColumnChanging>  
 <xref:System.Data.DataRow.SetColumnError%2A>  
 [<span data-ttu-id="a966d-118">DataGrid 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a966d-118">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
