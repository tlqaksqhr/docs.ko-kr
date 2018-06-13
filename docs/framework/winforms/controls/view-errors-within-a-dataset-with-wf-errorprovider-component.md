---
title: '방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- errors [Windows Forms], dataset errors
- error messages [Windows Forms], viewing in datasets
- ErrorProvider component [Windows Forms], dataset errors
ms.assetid: cbae023f-d651-4210-bdea-bcc5f037e321
ms.openlocfilehash: f00d874f2a4afcea3498a64fe946a93c83eb7b9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537088"
---
# <a name="how-to-view-errors-within-a-dataset-with-the-windows-forms-errorprovider-component"></a><span data-ttu-id="bf7cf-102">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 데이터 집합에 있는 오류 보기</span><span class="sxs-lookup"><span data-stu-id="bf7cf-102">How to: View Errors Within a DataSet with the Windows Forms ErrorProvider Component</span></span>
<span data-ttu-id="bf7cf-103">Windows Forms를 사용 하 여 <xref:System.Windows.Forms.ErrorProvider> 구성 요소는 데이터 집합 또는 다른 데이터 원본 내에서 열 오류를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf7cf-103">You can use the Windows Forms <xref:System.Windows.Forms.ErrorProvider> component to view column errors within a dataset or other data source.</span></span> <span data-ttu-id="bf7cf-104">에 대 한는 <xref:System.Windows.Forms.ErrorProvider> 오류를 표시 하려면 데이터, 폼의 구성 요소 수 있어서는 안 컨트롤와 직접 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7cf-104">For an <xref:System.Windows.Forms.ErrorProvider> component to display data errors on a form, it does not have to be directly associated with a control.</span></span> <span data-ttu-id="bf7cf-105">데이터 소스에 바인딩된 후에 동일한 데이터 원본에 바인딩되는 컨트롤 옆에 오류 아이콘이 표시할 수 있으며</span><span class="sxs-lookup"><span data-stu-id="bf7cf-105">Once it is bound to a data source, it can display an error icon next to any control that is bound to the same data source.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf7cf-106">오류 공급자를 변경 하는 경우 <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> 및 <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> 런타임 시 속성을 사용할지는 <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> 충돌을 방지 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="bf7cf-106">If you change the error provider's <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> and <xref:System.Windows.Forms.ErrorProvider.DataMember%2A> properties at run time, you should use the <xref:System.Windows.Forms.ErrorProvider.BindToDataAndErrors%2A> method to avoid conflicts.</span></span>  
  
### <a name="to-display-data-errors"></a><span data-ttu-id="bf7cf-107">데이터 오류를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="bf7cf-107">To display data errors</span></span>  
  
1.  <span data-ttu-id="bf7cf-108">구성 요소는 데이터 테이블 내에서 특정 열에 바인딩하십시오.</span><span class="sxs-lookup"><span data-stu-id="bf7cf-108">Bind the component to a specific column within a data table.</span></span>  
  
    ```vb  
    ' Assumes existence of DataSet1, DataTable1  
    TextBox1.DataBindings.Add("Text", DataSet1, "Customers.Name")  
    ErrorProvider1.DataSource = DataSet1  
    ErrorProvider1.DataMember = "Customers"  
    ```  
  
    ```csharp  
    // Assumes existence of DataSet1, DataTable1  
    textBox1.DataBindings.Add("Text", DataSet1, "Customers.Name");  
    errorProvider1.DataSource = DataSet1;  
    errorProvider1.DataMember = "Customers";  
    ```  
  
2.  <span data-ttu-id="bf7cf-109">설정의 <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> 속성 폼을 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7cf-109">Set the <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> property to the form.</span></span>  
  
    ```vb  
    ErrorProvider1.ContainerControl = Me  
    ```  
  
    ```csharp  
    errorProvider1.ContainerControl = this;  
    ```  
  
3.  <span data-ttu-id="bf7cf-110">열 오류가 있는 행을 현재 레코드의 위치를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf7cf-110">Set the position of the current record to a row that contains a column error.</span></span>  
  
    ```vb  
    DataTable1.Rows(5).SetColumnError("Name", "Bad data in this row.")  
    Me.BindingContext(DataTable1).Position = 5  
    ```  
  
    ```csharp  
    DataTable1.Rows[5].SetColumnError("Name", "Bad data in this row.");  
    this.BindingContext [DataTable1].Position = 5;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="bf7cf-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf7cf-111">See Also</span></span>  
 [<span data-ttu-id="bf7cf-112">ErrorProvider 구성 요소 개요</span><span class="sxs-lookup"><span data-stu-id="bf7cf-112">ErrorProvider Component Overview</span></span>](../../../../docs/framework/winforms/controls/errorprovider-component-overview-windows-forms.md)  
 [<span data-ttu-id="bf7cf-113">방법: Windows Forms ErrorProvider 구성 요소를 사용하여 폼 유효성에 대한 오류 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="bf7cf-113">How to: Display Error Icons for Form Validation with the Windows Forms ErrorProvider Component</span></span>](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)
